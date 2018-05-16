---
layout: post
title: First Post
excerpt_separator: "###"
---

In my first post I want to layout some of the ideas for this site as well as my current work/research projects. Here's where I'm at today:  

>DISCLAIMER - Not trying to be a Riot poser, just a big fan of this color scheme and this image was publically available  
>Night themes are just a better viewing experience 

### Projects  
**vBA Nessus Enrichment Script** - script written in vBA to take multiple Nessus outputs (in CSV), coalesce and enrich the data
     
>This is low priority at the moment. Not only have I moved from a vulnerability analysis role, but also 
>I'd like to devote more effort towards OpenVAS and it's integration with ELK stack and Metasploit 
>Framework. Nevertheless, the meat of the work is already done in [HypePKR](https://github.com/Bl00ve/HypePKR).
>All I would need to do is encapsulate it in a vBA executable.
     
*Completion Date - TBD*
          
          
**CVE Dictionary -> Snort/Suricata Rule** - python tool to take vulnerability output and create signatures based on CVE's found  

>Again, another tool which is more an effort of vulnerability analysis. I've searched everywhere for a tool that takes
>data from a vulnerability analysis and generates signatures to detect possible malicious traffic that could be
>compromising the found vulnerabilities. Might not make sense since you know the vulnerabilities already, thus why
>would you need to be alerted on something you fixed, but from a military standpoint it could provide leverage to
>implement some big configuration changes. I added in Suricata, just because I know it is basically the same thing as
>Snort, but at this point I'm too afraid to ask.
     
*Completion Date - TBD*
     
### Research
There is quite a bit to learn and I'm overwhelmed and excited. It's great that I have an opportunity to combine work objectives with
personal goals. That goal being to be relevant in today's cyber security work force. In that quest to be relevant below are the topics
I try to dedicate all my time to researching.  

**Docker**

>Container all the things

**Elastic Stack**

>There's a lot to learn so first and foremost, working on viewing data in Kibana and creating meaningful dashboards from pcap data
>(just Bro data for now).  
>Next step will be understanding the netflow, ingesting multiple file formats and creating beats, working with threading/clustering,
>and just understanding the stack in general. I should probably also look into SOF ELK from SANS and find it's use cases.

**Case Management**

>Namely Redmine or TheHive. I've never personally used case management so I need to define a workflow and how that workflow integrates 
>with other tools especially the ELK stack.

**Misc Topics**

>RockNSM  
>CAPESstack

I know there's more topics I want to look into, but that's all I can think of at the top of my head. I'll probably end up making this
into a separate page, but for now this'll do.

###### Side Note  
I am working on training for the majority of these topics to distribute to my colleagues, but I think I'll make more succinct, 
and less meme riddled white papers for myself. Also calling official memos or fancy memos white papers seems racist. I should probably 
research the origin of that.
<br />
<br />
<br />
This is enough for the first blog post. I'll try to make the formats a little nicer and plan these out better in the future. As well as 
creating a more targeted idea for the post.
