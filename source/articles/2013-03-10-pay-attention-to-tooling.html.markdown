# Thoughts on Tool writing
I once visited a museum focused on steam locomotives and by far the most interesting sections were on their construction. In that section, the most interesting artifacts were the tools. Building something so large made of steel, required *industrial* tooling - big, powerful, and dangerous. Just about every part on a steam engine is too large for a person to pick up or too hot to be touched, and so everything required mechanical help just to manuver it into place so they could heat it, hammer it, rivet or weld... they needed tools just to use other tools. This is also true of programmers, who have managed to build systems both complicated and fragile, with little hope of being able to control or manipulate without tooling. Ours is a virtual world and so instead of metal we have the weight of complexity. So we still need tooling to get the job done - the problem isn't in the shaping anymore, it's usually the discovery. We're dealing with something far too large to hold in our minds, moving to fast for us to comprehend. If we want to maintain control of our creations, we'll need to build the tools to harness all of this speed and complexity. 

## Be a cheerleader
Many of your best developers and system engineers will naturally create tooling for repetitive tasks to make their lives easier. If you've got a team where nobody is tinkering around on this kind of thing, my advice is to be worried. Building something that requires more than an individual means the odds are in your favor that what you'll end up with is something complicated, and in need of maintenance.

*"Another flaw in the human character is that everybody wants to build and nobody wants to do maintenance."* - Kurt Vonnegut

Being a good manager is often times about being a cheerleader for the things you want to see happen. Show an interest when people are writing scripts to help them out. Ask them how it works, be excited and encouraging, but also give them feedback when you're worried. Not all tools are created equal, so some caution about what's being created is necessary. Above all the most helpful thing you can probably do is to ask them to document the tool for others. Hopefully your team has a troubleshooting/how-to/cookbook/run-book section for the members of the team. Ask them to document the tool in an appropriate place so that others can make use of it. Make sure the tool is available for sharing. That might mean it's available in git, or it might mean that you have an "Admin Tools" package that you distribute to your application servers. If the tool has merit, your goal as the manager is to make it as easy as possible for others to discover and use. Finally, ask the author to do a demo for the team. This could be a 10 minute thing after stand-up, or a half hour meeting, or something larger. It's a great way to recognize and encourage the behavior.

## Industrial grade tooling is dangerous
 
+ You need to encourage your tool to automate heavy lifting with tooling
+ You're engineers will write industrial-grade tooling
+ There isn't an ocia for developer tools
+ You got to get them to consumer grade
