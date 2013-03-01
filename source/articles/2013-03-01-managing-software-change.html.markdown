--- 
title: "Deploying Large Scale Software Part1:Theory"
description: "One of the best parts of my job is that I get to work on really big systems. I love the scaling problems I encounter, and as a manager they don't go away. Let's talk about a process that's at the intersection of technology and human judgment: how to upgrade large pieces of software."
date: 2013-03-01 
popular: false
published: true
tags: management, process
---

# Well There's Your Problem Right There!
Software has thankfully moved away from the shrink wrapped distribution model, and into a continuously updating, always available online model. Web services, cloud computing, mobile, and a whole bunch of other buzz words from the past decade have further increased the size and complexity of software, creating a need to grow horizontally - past a single computer and on to tens, hundreds, thousands... and beyond. 

Horizontal growth of applications has drastically increased the complexity and risk of deploying and changing software. Gone are the days where an individual "release engineer" can realistically deploy software in a manual or ad-hoc fashion. Software deployments and the manual processes around them are now a leading source of outages (http://www.cs.cmu.edu/~priya/PDL-CMU-05-109.pdf) for any sufficiently complex system. As the manager of a team running production services, I end up thinking about this topic a lot. Nothing will kill a great product quicker than flakey availability, unless you're twitter (sorry I had to). 

But wait it gets worse. In addition to the growing risks involved in deploying software, the industry is trending towards more frequent deployments. Take a quick look at my "[the best parts of agile](/articles/2013/01/10/best-parts-of-agile.html "The Best Parts of Agile")" article, and it's easy to see that the only way to deliver small pieces to your customers quickly is to ''deploy software frequently''. Even if you're not on the agile clue train, your still updating more than you used to. The Internet doesn't release a new version of software [once a year](http://techreport.com/news/23414/rumor-microsoft-may-hasten-windows-release-cycle), if you're slow you release monthly. That alone is an order of magnitude faster than the days of boxed software. 

# Things are bad, So What's a girl to do?

As the dev manager, you're on the hook to make sure that in spite of all the extra opportunity for failure, it doesn't happen. Let's start with what I'll call the deployment mindset. If you can develop the right belief system on your team around deploying software, most people will end up doing the right thing automatically. Here's the dogma for our new belief system:

## Your problem isn't quality. Start with an assumption that all software is broken.

It's a typical reaction when you have a bad deployment to redouble your efforts on raising the quality bar of the team's software. Surely if we just get *a little better* at programming cautiously, or if we add just *a few more tests* this kind of thing won't happen. Wrong. It will. The deck is stacked against even the best, most defensive programmers. Each extra line if code is an opportunity for a bad interaction with what is surely a large and complicated system. Don't stop testing or try to improve, but admit that you're never going to be able to account for all failure modes. Even if you have a good day and you nail it, can you do it again tomorrow? Next week? Every day for the next 3 years? You have to start with the assumption that what you're about to deploy has a bug in it.  

## Configuration is more dangerous than code.

Code, you're paying attention to that. You've got a test environment and that's helping. But what about all the stuff that changes in production? Service endpoints, deployment settings, a different database, different caches, different application configuration, different... everything. Sure, it's more difficult to get this stuff wrong, because it's a couple lines of code sprinkled in a few well understood places (hah!). But when you DO get it wrong (you will. plan for failure), you've just caused a system-wide outage. The blast radius of a configuration change can be *huge*, so why are you waiting to production to find out you mistyped something, or that we changed the naming convention, or that the new endpoint isn't up because we deployed in the wrong order. That can't happen, so just start planning for how you verify configuration changes to production before it takes down the whole fleet. 

## Threat models aren't just for security breaches. 

Threat model your release process. No I'm being serious, go get everyone on your team, and ask them to assume that every part of the process is broken. Ask them how we find out about it, ask them how far down the release process the bad change gets before we stop it. What was the blast radius? Did every customer experience an outage? Ask them how many opportunities we gave yourselves to find the problem before it's running on every production host in the fleet. You should bake redundancy into your verification steps, maybe the 2nd level alarm happens to catch a problem that the testing didn't. I'm sure glad we added that. 

## You're **still** going to have a bad day. Reduce thy blast radius.












