---
layout: post
title: "Project: Jacobi... and other things"
---

Lots of exciting things happening soon, and I've taken a break from blogging the past couple weeks because Air Force things, memorial day 
break, coding, etc. So I wanna go over a little bit of my work with Jacobi (my project I went over in the post "Rorschachs Journal") and 
talk about some things to come and current projects.  

### Jacobi  
Well I went over a bit of the current challenges I was having in the previous post with getting the tool to work in Bash, and since then 
I abandoned trying to do it that way since there was too many issues with assigning global variables. Maybe there is a way to do it, but I 
know Python handles those things better just by virtue of it being object oriented (even though I'm ass at OOP, but getting better).  

Nevertheless, jump to present day and I built a pretty dope curses menu (well stole [with credit given] from a Github page) and have 
figured out the starttime/stoptime problem. It turns out they were using Epoch time, but with a couple hours offset. Not really sure why 
anyone would do that, but it wasn't too hard to program that out. Now my main issue with the time piece is placing in timezone variables 
and having it dynamically offset based on that. The tz module takes care of that, but for the time being hard coded works while I work on 
the actual queries. I wrote out the queries and the associated variables they would need today and coded one, plus moved the menu around 
a bit (which actually turned out to be a lot more difficult than I thought). I've been having so many issues with working around indents 
and keeping my place in the code. A decent IDE is all I need, yet I have none available...FML. Gonna try and work on that with some of the 
program managers and see if we can make something happen. In closing, main parts that need work are building out the queries and making 
sure to comment enough for someone to go in and edit what they need when the time comes.  

### Dreamhack!  
This weekend is Dreamhack in Austin and I'm pretty excited to go and actually play in the BYOC (bring your own console [even though it's 
PC]). There is a League and PUBG tournament I hope to find a team for since the prize pools are pretty huge, but finding people to play 
with regardless would be sweet. Not much else to say about that.  

### Misc  
As far as other things going on, here's what's going on in my neck of the woods:  

> 1. Still chugging on OSCP. I've been researching buffer overflows, but it's difficult to practice just on any executable just because
there is so many to choose from. The task is big and feels daunting, but I guess just picking some standard Win/Linux files should be good 
enough. That's what tomorrow will be for me.  
> 2. After seeing some of Riot Gradius' Github, I've been inspired to make an at-home NSM solution. I want to use Security Onion, and get 
comfortable on the tools innately on it, and create my own to fill in the gaps. 
> 3. As part of my pet project to impress Riot folks I started doing some persona mapping and trying to prepare a semi-pentest(ish) (wow, 
that's a lot of qualifiers) portfolio. It's difficult to make something like that and A - not seem creepy, and B - not be a dick and do 
an actual pentest without letting anyone know which would not be cool. So my basic idea is to submit something to the bug bounty program 
which would go over persona vulnerabilities. I could attach some cute documentation with League graphics to bring to light any issues I 
find. That is... if I find any.  

I want to post some of the links I used for developing my newest builds of Jacobi, but they are all at work. So I'll update this later. 
Oh also meant to mention this earlier, but this is my first tool that isn't named after a LoL ability. It probably wouldn't be cute to 
name them all after LoL anyway...
