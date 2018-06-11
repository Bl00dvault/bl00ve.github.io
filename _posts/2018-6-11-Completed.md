---
layout: post
title: Complete! ...sorta
---

## All of the Projects  
I finished Jacobi this past week on Wed or Thursday, I don't really remember anymore. I had a lot of fun on my first big Python project.
As a reminder this was my project to create a dashboard for using Moloch a network packet analyzer. Of course the majority of the time was 
spent with adding error checking and making sure it was Air Force proof, however all that still taught me a lot about the ins and outs of 
programming in Python. I used a curses menu to setup the front end navigation and that seemed to work well enough, but kind of a pain in 
the ass. I'd like to add some cute ASCII art or something to jazz it up, but I guess curses is good enough with its default layout. 
The program isn't exactly finished, but the only thing it's missing is more queries. I think I have the majority of the error checking out 
the way with only a few minor spots that are pretty hard to reproduce. As far as work goes, it's a good enough project to start people out 
using Moloch so I'm on to bigger and better things.  

## Bigger and Better Things  
So I had a wild hair on Thursday night and decided to work on an idea I had probably almost a year ago. I wanted to create a better 
relationship between our vulnerability analysis team and network operations team so I figured there must be some way to make vulnerability 
data more useful. The easiest kill is taking CVE's present on vulnerable hosts and using them to create Snort rules to detect if those 
CVE's were attemped to be exploited. That sentence sounds terrible, but I can't think of another way to phrase it and you know what I mean.
To get this into a tool my original thoughts was ingesting both data sets into SQL and trying a query that way, but making that 
implementation reproducable (sp?) for the average joe would be too much work. So here come's CVE-Sweeper!  

## CVE-Sweeper  
This name is the least exciting of all the tools I've come up with so far, but it does the trick. Somewhat of an homage to the sweeper lens
 from League, and I think that's good enough. Basically I just takes the dictionary or Nessus output in CSV format, and correlates it to 
 the Snort community rules where the "reference:cve," is set. It then populates a nice little output with the list of IPs in the Nessus 
 scan, the CVE's that are called out for readability and a total number of rules generated. That last part is because I wanted to start 
 having my programs write my EPR bullets for me. Neat huh? In the output with the list of IPs generated it's based off the total IPs listed
 in the Nessus output which isn't the most targeted approach. However Snort is based off alerts and vulnerabilities can be exploited a 
number of different ways so that might be the best choice. Not sure, so if someone with more insight disagrees I'll look to change it.  

## All Work and No Play  

![Dwight](/images/dwight1.png)  

...makes Bloove a dull boy  

### Dreamhack  
Dreamhack was a pretty big disappointment mostly because I went with the sole purpose of playing in the LAN tournaments and getting to 
game with a bunch of nerds in person. Unfortunately, between the power outtages and internet quality I wasn't able to do much of 
anything on the LAN side of the house. The PUBG tournament was pretty cool, I got to try a neat new game called [Wormhole Wars](discord.gg/wormholewars) 
which you can get for free too (use the link and go to the "Key Request" channel), and learned of a LAN cafe in San Antonio because I 
played the owner in Overwatch. Overall, it was too much of a bummer to go back the other 2 days since I could just watch all that stuff 
at home, but thankfully I only live an hour away.  

### Gaming News  
So my newest obsession is Realm Royale. It's a pretty awesome installment in the battle royale genre. It's not quite as whimsical as Fortnite 
and isn't nearly as realistic as PUBG. Plus, I'm pretty good at it so that always makes a game more enjoyable. Climbed up to Diamond 3 in 
the first weekend so either I'm decent or this game is easy. Will update once I hit Masters to let you know how bad I am, ecks dee.
  
