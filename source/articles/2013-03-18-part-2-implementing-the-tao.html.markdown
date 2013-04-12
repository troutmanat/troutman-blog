--- 
title: "Part 2: How to Implement the Tao of Software Change"
description: "Building off of our previous article on how to create an operational culture around software deployment, let's look at how to implement such a process as the Tao suggests." 
date: 2013-03-18
popular: false
published: true
tags: management, process
---

If you haven't already, go read [the first part](/articles/2013/03/05/the-tao-of-software-change.html) of this series to understand the mindset for developing a rock-solid release process. I encourage you to wrap your head around the culture first, because if you're not bought in on the ideas then the implementation isn't going to happen for you. If you're already on the road, then let's continue forward and learn the details of how to build a release process aligned with the Tao. 

# On Testing
The Tao is very quick to point out that testing can not, by itself, save you from having a bad day. That doesn't mean you shouldn't test things, but you need to be strategic about it.

## Testing Core functionality
I'm not going to go into this, but rest assured: if you're not automatically testing the basic functionality of your software every time you make a change, you're doomed in ways I can't begin to explain. There are no excuses. Figure out what the core functionality is, and have functional tests to validate the common usage patterns your customers will perform. 

## Clean State
Many people will ignore this advice because it's hard, but make sure all of your tests run independently, and don't depend on state from previous runs. Yes, the tests take longer, yes, there is more setup and tear down code. Get over it. This up front effort pays for itself a million times over by creating tests that are easy to troubleshoot, easy to debug, and accurately highlight failure. 

If your tests are unpredictable or fail in flaky ways, people learn to ignore or retry test rather than investigate. It's almost as if the test are useless... wait that's exactly what they are.  

## Long-Running is Bad
Test suites that balloon to hours per run become ignored, or paired down to the important tests. Save yourself the effort of writing lots of redundant or nuanced tests that don't validate customer behavior.

I'm not a believer in the need to test for everything. I think test coverage is a poor metric for quality and focuses on testing implementation details instead of the API contract. If you find an obscure bug after a feature has been out for months/years, you should fix the code, but adding a test that you'll run *every time you deploy* is overkill. Sure, write a test harness to help you debug the fix, but be prudent about what makes it into your deployment validation process. If you must run those obscure tests, do it out of band.

## Measure Functionality Before and After the Change
More important than functional or unit testing is measuring the change in core metrics between the stable version of software, and the one you're rolling out. The particular metrics you care about will vary, but at a minimum I recommend taking a look at error rates and latency which are foundational to the customer experience.

Come up with some way of measuring the average steady state of your core metrics across the software fleet. Most monitoring packages like ganglia or nagios can handle this for you. Now deploy your software change to some portion of your fleet. Compare the established average to your new software and note how they've changed. Any sort of change outside of a standard deviation (in either direction!) is probably worth investigating before you proceed. Big changes are bad, they usually mean something unexpected is happening, or that your new software behaves differently than the old. The Tao has taught you to be cautious, and so you'll take the time to understand what's happening before you move on. 

# Tiny Little Pieces
I'm going to refer again to my [best parts of agile](/articles/2013/01/10/best-parts-of-agile.html) article, because agile thinking works just as well for deploying software as it does for writing it. We want to break down our changes into tiny little pieces. By breaking things into small pieces and using real time feedback from metrics, the cost of a rollback is a small effort. Deploy 12 changes at the same time and need to roll back? You've got a lot of investigating to do. Deploy one thing at a time? Finding the impact is a much smaller undertaking. 

But you can take it further. Your software should be in small pieces, and so should the number of customers seeing the change. Expose the update slowly at first - let it bake on a small user set and build confidence as more and more customers use your new software. Increasing the rate at which you roll out the change as you expose it to more customers without issue. You can break up your customers by geographic region, size, or some other metric. The Tao has taught us what a bad idea it is to increase the blast radius. Just like software change, it's the same thinking: break the work into small pieces, use feedback to guide your decision making, get good at iterating fast (more on step 3 below). 

I've found 2 techniques that work well for breaking your users into small pieces:

## One Box Testing
The idea of one box testing is simple - before rolling out a change to your entire production fleet, have a single host receive the change first. Remember, the Tao has taught us to be skeptical of configuration, which means we should configure the test host *exactly* like the other production hosts. It should even be bound to the same loadbalancer, and receive the same portion of traffic. It's the same in every way, except it gets our software change first. Then we can automatically compare our software change to the rest of the hosts, just like I recommend in the testing section above. 

Pros:
* Test config before it goes to production.
* Relatively easy to configure and implement. 
* Easy to set up as part of a continuous integration framework.

Cons:
* If you're running an application on a single host, it costs you more money. 
* You don't control which users see it, and "undo" is accomplished by rolling the change back.

## Deploy Disabled, Dial Up
The second approach I've seen employed to good effect is to instrument changes in a disabled state, and then have a mechanism for dialing up the exposure manually. There are a bunch of ways to control the dial up, but which ever you choose, the strategy is to deploy to the entire fleet, then slowly ramp up exposure while monitoring your key metrics as above. 

Pros:
* fine grain control of the dialing up process.
* Easy to "dial down" in case things start looking bad.
* Works on a fleet of 1 host. 

Cons:
* You have to instrument your code, and build a system for dialing up/down the customer exposure.
* A bit more complicated, and can end up relying on extra configuration if you're not careful. 
* You don't test configuration till it's deploying to production. 

## Peanut Butter & Chocolate, Boom.
There's no reason you can't combine these practices and get added benefit. Use one-pod to validate configuration before everyone gets it, and use a dial-up methodology to test more ambitious changes that you'll want to fiddle with a lot. If you don't have the time to implement both, I recommend one-box as the easier first step, then you can add more functionality later. 

# Automate Everything. 
So if you've been following along to this point, you're no doubt realizing that this is a lot of process around software deployment. You're going to run all kinds of testing, you're going to deploy to a portion of your fleet and measure key metrics for regressions, then you're going to roll out to another portion and do it again. You'll have to roll back and start the whole thing over if anything goes wrong. Oh, and you're going to break your changes into tiny pieces so you'll have to do this pretty much all the time. 

*This is going to suck*. And you're right, except for one saving grace: we're not going to be doing any of this ourselves. The most important aspect of your deployment process is going to be setting it up inside of some sort of continuous integration system, or other workflow service. Again, the Tao has taught us to not trust ourselves - doing all of this work is a long and tedious process that's much better suited to a computer. A computer can compare metrics and decide to roll back changes or deploy to the next set of hosts. It can also run your functional tests and compare results, and it doesn't mind doing all this work on tiny little changes. It can email or send an SMS message any time a person needs to get involved, but not a moment sooner. You would be a fool to not pay the cost to set up such a system. It will save you time and reduce the impact of bad software changes. It will also reduce the number of careless mistakes a human can make, which we can say is a good thing. 

# With Great Efforts Come Great Reward
So to reiterate: We're going to take what used to be a monolithic software change and we're going to break it down into pieces. We're going to break down the customer base as well as the amount of change happening in a single deployment - smooth it out, and have it flow slowly through the entire fleet. Along the way we're going to run our functional testing, but we're also going to verify our configuration changes works by testing them on a single host. Once we have the change on a portion of our fleet, we're going to compare results to our last known good state, and make a decision to roll back or deploy a little bit more. We're going to automate this whole process so we can be sure it gets done properly. 

No doubt it's a ton of work, but it will be worth the effort. Why? Because you're going to be able to move changes to production safer, with less engineering involvement. Because your engineers aren't spending hours nannying changes (poorly) through the system, they're getting more done. And because they're getting things done, so are you, and with less bad days. You'll thank me later, trust that the effort is worth it.
