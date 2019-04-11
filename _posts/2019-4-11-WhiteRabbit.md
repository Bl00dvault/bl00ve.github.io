---
layout: post
title: White Rabbit Pt. 1
---

So here's my plan for my upcoming project. I'm going to outline my idea using the JP-5 format as to help cement my understanding and to practice a bit for work. Without further ado...

### Situation
This application, named White Rabbit (for now), is being designed for my new unit and because I've seen a constant issue with operations requiring a test environment for applications, malware, and metric gathering. There are a lot of applications that can cover aspects of these, but nothing that I've found that focuses on creating a user friendly front end for creating a virtual environment. 

End State- A user friendly application with a front end capable of quickly deploying a virtual environment on any major virtual host application (ESXi, VirtualBox, VMWare). The deployment will also have the ability to generate a network map, capture network transport metrics, and deploy simulated business functions such as Exchange, Database, and other Active Directory content. 

Risk - Security concerns are at a low priority since most lab environments don't have an affect on operations. Also this is intended to be internal and to be protected by any other internal network protection (i.e. firewalls, gateway router, DMZ)

Assumptions - User-friendly is defined as someone who has a basic networking understanding and is familiar with creating and configuring a single virtual machine.

Legal Considerations - Not sure on the name, but I'll end up using an open source GNU license for this (pretty sure that's what it's called, will need to do some research)

### Mission
The objectives and tasks to be accomplished are outlined as follows:

OO: Develop application to create virtual environments

TO: Application will be user friendly
  TT: Establish compatibility across all major virtual host platforms (VirtualBox, ESXi, VMWare)
  TT: Create GUI for administration and initial setup
  TT: Deploy administration functions (setting up default accounts, AD, routing/firewall rules)
  
TO: Application will develop application testing environment
  TT: Generate business functions as needed
    Note- Need to set predefined business functions (Windows/Linux, Active Directory, Exchange, Database, etc)
    
TO: Application will provide in depth network characteristics
  TT: Generate network map
  
(Work in Progress, I'll come back and update this if necessary)

### Execution

Phase 1 : Research and Development
Need to research any other similiar applications (possibly paid for applications that do something similar). Also have to reinforce my Ansible syntax and make sure that this can define administration functions as well as VM deployment (also compatibility with ESXi and other apps). 

Phase 2: Range Deployment

Phase 3: Range Characteristics

Phase 4: Front End/ Usability Requirements

Phase 5: Testing

Phase 6: Production/Distribution

### Admin/Logistics
I'll be the primary engineer and coder for this project and will host this on Github. Not much more to go into than that.

### Contingencies
Not sure where to go with this, other than I might have to scrap the project if I find something much easier to use with either a low cost or there may be some functionality I'd have to phase out. This is fairly simple and minimum difficulty to what I already know of Ansible. Might build this out more later too.


### Closing Thoughts
Probably shouldn't try to build these out at 4am...
