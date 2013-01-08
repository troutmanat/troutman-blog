--- 
title: "Being Effective: Understanding the value of mechanisms, and when to get by with rules instead." 
date: 2013-01-07 
published: false
tags: effectiveness,problem solving,risk mitigation
--- 

Problems repeat themselves. A big part of being effective is learning how to stop solving the same problem again and again and instead move on to the next issue. Most people can fix a problem as it occurs, but the tougher skill is to *resolve* the issue for good.

## The danger of relying on good intentions

Tell me if this has happened on your team: 
1. A problem emerges - for this example let's use something simple like "people aren't including testing with their code when they check it in"
2. You discuss it as a team - EVERYONE is practically falling over one another in agreement, this will NOT be tolerated in the house of the holy, no way. 
3. A **zero tolerance policy** is put in place - If somebody submits code without tests, bad things will happen, bonds broken, nobody even wants to consider the consequences but we're all in agreement that it's never going to happen again. 
4. 2 days later code is submitted without any testing. Somebody forgot to do *git add -A* on their new test files. Or maybe "the change was so small, it didn't really need tests" maybe.

Begin by admitting to yourself that asking people to change, even if they AGREE with the suggestion is a low-probability event. Worse still, even if you have an extremely motivated and passionate team, they're likely not a team of robots (If you run a team of robots please email me, **I want to know more**) and will eventually make mistakes when trying to apply a policy. Expecting the right thing to consistently happen just because everyone agrees, and even wants the outcome is nothing more than relying on good intentions, which will eventually result in the reemergence of a problem. 

## What we want is a mechanism that nobody every has to think about if things are going well

Sticking with our code testing example, the solution wasn't to get everyone to agree that code must be tested, it's to make sure that when code isn't tested, the submitter isn't successful. In this example, maybe the solution is a pre-commit hook that validates the code includes changes to test files, or maybe you're one of those insane teams that has code coverage metrics. Regardless of the reason, a failure to test new code results in a localized failure for the individual. The intended outcome is always achieved, no matter what the mistake or omission.

The take away is that if you want to really solve problems in a long term fashion, you have to render them down to the important outcome, and then automate a mechanism to prevent the outcome from being achieved if conditions aren't met. That is of course much easier said then done, and so my parting advice is to learn to pick your fights. 

## Sometimes a rule or a policy is good enough

Being effective means you get the important outcome when it counts, it doesn't mean that you'll solve every bit of minutia that floats your way. Don't try to establish a mechanism for every problem, identify the problems that are worth spending the time on. I think the code testing example above is a problem I would spend the time setting up a mechanism for. Why?

* It's a problem with high periodicity - there are a lot of opportunities to make a mistake and have the problem re-emerge
* Failure to solve this problem has large consequences - who wants to write an email to their boss explaining that you had a 20 minute outage because you pushed bad code? Not me...
* The likelihood that not solving the problem will lead to larger problems is high - You have to make a gut call on some things and decide how likely it really is to cause an issue. Sometimes the answer is "not very likely" and in those cases living with the risk might be OK. 

In cases where a mechanism is judged to be overkill, fall back to good intentions but make sure to capture them in some centrally accessible place, like a team wiki page. Getting an entire team to check a "policy" page cuts down on interruption, saves cycles, and reduces ambiguity, but that's perhaps a topic for another time...
