---
layout: post
title: vFeed Me
---

Just wanted to write down some of my ideas to coincide with my recent discovery of the vFeed database. I want to be able to take the data it provides and create more products that are actually useful for all members of my team. Currently, vulnerability data is only processed and by processed I mean an operator reads the criticality of each finding and arbitrarily ranks the highest vulnerabilities for a customer to prioritize. My machine learning project (mentioned in the last blog post) is aimed at trying to address that issue, but I feel I can use the vFeed data to create products for the other teams to use including an attack vector memo and possibly diagram to display vulnerabilities with appropriate exploits across exploitdb, milw0rm, MetaSploitFramework and use the Mitre information provided to address the attack vector when necessary. Actually, let me break these products down and use the table names for my thought process sake. For reference you can check out this cool website ([SQLDbm](https://app.sqldbm.com/SQLServer/Share/3yEY6QpkexLZVvaNzDZD_kGFrngIE8md_DYjF4jNYw0)) I found which lets you map databases in browser.  

## Attack Vectors  
    Tables - map_cve_nmap, combined_vendor_security_patch, map_cve_saint, map_cve_milw0rm, map_cve_exploitdb, map_cve_msf, cwe_capec, capec_db  
This product would display:  
- NMAP NSE Scripts - To provide a method for validating vulnerabilities found using NMAP.  
- Vendor Security Patch - Since most patches include a proof of concept with exploitation, well sometimes at least.  
- Saint Exploits - Apparently this is another tool which appears similar to MetaSploit. I haven't personally seen it, but it could be worth looking into. For [reference](http://www.saintcorporation.com/products/penetration-testing/)...  
- Milw0rm Exploit Db - This was a site similar to exploit-db which closed up shop in [2009](https://www.darkreading.com/risk/hacking-and-exploit-site-milw0rm-closes-its-doors/d/d-id/1131477). Since some equipment we encounter is dated this might still be a useful resource.
- Exploit Db - Obviously the go-to exploit research [site](https://www.exploit-db.com/), including information in a single product would just avoid a Google search and get the information out faster.  
- MetaSploit Framework - Again the go-to exploit framework which again, would pretty much just save a Google search.
- Common Attack Pattern Enumeration and Classification (CAPEC) - Provides attack vector information based on certain information. Might need to correlate with more information from the CAPEC [site](https://capec.mitre.org/data/index.html).  

## IDS Indicators  
    Tables - map_cve_suricata, map_cve_snort
Don't really need to explain these tables. Both are network vulnerability detection tools which we could use the host vulnerability data to possibly detect nefarious traffic. This is pretty much what my other tool [CVE-Sweeper](https://github.com/Bl00ve/CVE-Sweeper) does so I'll probably retire that in favor of this implementation, or combine the efforts.  

## Vulnerability Information  
    Tables - nvd_db, map_cve_iavm, combined_vendor_security_patch, map_cve_certvn, capec_mit, capec_db
The goal here is to provide a comprehensive vulnerability picture of a customer's network. I'd like to be able to correlate attack vectors with a host's relative position in the network to help prioritze vulnerability mitigations. This is the part I want to try and use machine learning some how to predict maybe where an attack will come from. I'm still trying to think out where I would find the information to learn from. Whether I use previous customer data or something. I'll go further into detail when I get better at the whole concept.  

That's all I have to say about that.
