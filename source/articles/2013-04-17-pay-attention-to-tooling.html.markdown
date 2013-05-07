--- 
title: "Pay Attention to the Tools Your Team Writes"
description: "Maintaining software requires customer tooling to be written. Encourage your team to write tools to do their job, but also be cautious about what they end up creating." 
date: 2013-04-17
popular: false
published: true
tags: tooling, management
---

# Thoughts on Tool Writing
I once visited a museum focused on steam locomotives and by far the most interesting section was on their construction. Just about every part on a steam engine was too large for a person to pick up or too hot to be touched, and so doing anything required mechanical help. If a worker needed to maneuver, heat, hammer, rivet or weld they needed special tools - large and dangerous to accomplish the task. When I got my first chance to work on a software system that I didn't completely write myself, it was much the same story. An engineering team is often dealing with something far too large to hold in our minds, moving too fast for us to comprehend. If we want to maintain control of our creations, we have to build tools to harness the speed and complexity. 

## Be a cheerleader
Many of the best developers and system engineers will naturally create tooling to make their lives easier. If you manage a team where nobody is tinkering around on this kind of thing, my advice is to be worried. Building anything of consequence  means the odds are in your favor that what you'll end up with is something complicated, and in need of maintenance.

*"Another flaw in the human character is that everybody wants to build and nobody wants to do maintenance."* - Kurt Vonnegut

Being a good manager is often times about being a cheerleader for the things you want to see happen. Show an interest when people are writing scripts to do their job. Ask them how it works, be excited and encouraging, but also give feedback when you're worried. Not all tools are created equal, some caution about what's being created is healthy. Above all the most helpful thing you can do is to ask them to document the tool in an appropriate place so that others can make use of it. Make sure the tool is available for sharing. That might mean it's available in git, or it might mean that you have an "Admin Tools" package that you distribute to your application servers. If the tool has merit, your goal as the manager is to make it as easy as possible for others to discover and use. Finally, ask the author to do a demo for the team. This could be a 10 minute thing after stand-up, or a half hour meeting, or something larger. It's a great way to recognize and encourage the behavior.

## Industrial grade tooling is dangerous
There is no [OSHA](http://www.osha.gov/) for software development, the best we have turns out to be front-line managers. If you leave it solely to your engineering team to write tools to do their job, you'll end up with industrial grade tooling. It will be powerful, broadly applicable, complicated, and able to destroy your application at a moment's notice without so much as a confirmation dialog. Your team is a group of **software professionals** they are writing tools for themselves, not the novice and so they're not bothering with things like a chain guard or automatic shutoff. Why would they? You're asking them to move fast every day, and that stuff just slows them down. *They* know how the tool is supposed to work, so it's not a problem. 

But of course it is a problem, and you know that. Massive, embarrassing outages emerge from mistakes at 3am with an industrial-grade tool. It's so easy to fat finger a command, or to run something in the pressure of the moment that makes things worse. I once had a tool which would allow me to SSH on to thousands of instances, as root, and execute any commands I cared to. What a doom bringer that thing was, but at the time I remember thinking how much time it was going to save me.

And that's why the manager of the team needs to be OSHA, she needs to come in and audit the tools, and issue safety violations where appropriate. Here are some of the critical regulations of tool writing that I always like to consider when learning about something my team is writing:

* Is it read only? If so, does it use multiple connections in parallel? How many? Is there a hard limit?
* What resources does it consume? CPU? Memory? Disk IO? How aggressively does it use these resources, and for how long?
* Are there limits to the amount of data it can change with a single command? Are the limits small?
* Does the tool delete data? Could it instead archive the data?
* Does the tool update data? Could it instead archive and replace?
* Can you manipulate arbitrary data, or does the tool control what information is changed?
* Is the tool access controlled, or can anyone run it? 
* Does the tool have elevated privileges? Where is the account info stored for the tool? Is it easy to steal?
* Can the tool run anywhere? Is it compartmentalized to test environments only?
* Is the tool and all of its options documented? 
* Is it installed in a usable place? Is that place centralized or on every device? 
* Is the tool run on-demand or can it be set up to periodically run?

Running through a set of questions like these helps everyone get on the same page about what kind of tool we're building. The goal isn't necessarily to water down the effectiveness of tools, but you should know what you're dealing with. If the team has industrial grade tools, know about them, and figure out how to limit their usage. In some cases, the answer might be that you need 2 people to be able to run certain tools, or that you can only run a tool for a certain number of times before it locks up and you need to get a manager involved. If a tool has the potential for big impact, there needs to be sufficient inertia in place to cause people to question whether or not they really need to use it. The goal isn't always to get rid of these tools, but to make sure brains are turned on before they get access. Asking people to contact a peer or a manager is a great way to bake in that level of engagement. 
 
Be a cheerleader for tool writing on your team, it's a guaranteed way to increase productivity and correctness. Hold expectations high and stay engaged, you're in charge of safety for the team's application. Play the part of OSHA and make sure people aren't building dangerous tools. Make sure usage of powerful tools is scrutinized on the team by making others involved before they can be used. Don't go overboard and let fear get in the way of creating a culture of tinkerers, the best results come from experimentation and building, but the best experimentation doesn't happen in production.
