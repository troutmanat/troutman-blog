--- 
title: "Document that which can be done"
description: "Like it or not, automatically generated documentation isn't enough value to the customer. We need to write opinionated documentation on how we expect people to use our software."
date: 2011-01-19 
published: true 
tags: management
--- 

The project is done! Pop the champagne, hand me a party hat, and wake up
the boss, it's time to celebrate! Wait. We forgot about documentation?
Really? What about all that automatically generated stuff! I put in the
javadoc/rdoc/doxygen/ POD docs/etc.... surely that counts right? No?!
Stop shaking the boss you say? Documentation is the [rare earth
metal](http://en.wikipedia.org/wiki/Rare_earth_element) of software
engineering: in limited supply and extremely valuable if you can find
the good stuff. So what exactly is the "good" documentation? With the
precious few moments you'll be able to dedicate to documenting, focus on
actionable content: document that which can be done. When software is
providing value, it's doing so by saving others effort. Documentation
should first answer this question: What work can you do for me? Treat it
as an opportunity to show the customer how the work you've done can make
them look good.

Nobody ever says "let me see your javadoc"
------------------------------------------

Automatically generated documentation is extremely cheap to create. This
is good, cause you get what you pay for. Specifics about a method,
class, or interface is extremely important information for people who
already know how to use an application. Nobody learns from this kind of
documentation, because it isn't coherent or engaging. And that gets to
the heart of the matter: don't give customers reference material when
what they've come looking for is an excuse to use your product. We
should all try to write documentation that first inspires, then enables.
Worry about the gory details later. If you find yourself chortling at
the idea that anyone could be inspired by documentation, it's likely
cause most documentation just plain sucks. It contains none of the the
unique character that went into making the software, and it takes a dry
formalized tone which instantly disengages people. I think we all like
the idea of write documentation to show off our own efforts: "Look what
I made, see how complex it is? Here's a "high level overview" so you can
try to wrap your head around it. Here's how to contact me, your going to
have a LOT of questions, trust me... Oh, here's the API, and here is a
FAQ containing stuff nobody has ever asked me, but I think they should
cause it's confusing, and I didn't explain it anywhere". What part of
that experience makes people want to learn?

Make documentation about the customer, everyone loves themselves
----------------------------------------------------------------

The documentation I described above completely misses the mark because
it's about what the developer has done, and not what someone else can
do. People care about themselves, so use that to our advantage, and
write documentation to show them how to be a superstar. Here's how:

1.  **Start with a commercial -**The first section of documentation
    should be a commercial for the product. Start off by showing people
    the best example we've got for how the application is going to save
    them work. The first section is the hook, make people excited with
    the possibility that **they will look like a hero for using our
    product.**Many open source projects have started doing this, go to
    the ruby on rails website and the first thing you'll see is a
    section called "Get Excited".
2.  **Keep up the momentum with examples that build on each other** -
    Show people a wheel that spins straw into gold and the first things
    out of their mouths will be "what else does it do?" Keep people
    excited by diving right in to some examples. Start with how to do
    the basics, and build out the complexity from there.
3.  **Be opinionated -**We're not writing a Wikipedia article, so try to
    avoid saying things like "there are several options for configuring
    your Flamdoodle app, each with pros and cons". Nonsense! Nobody
    started reading the documentation because they wanted more options
    for configuring Flamdoodles, they cam to us for answers. So let's
    step up and give them one: "Although there are many ways to
    configure the Flamdoodle, we find that most prefer using the
    Foodidle wizard". When that dark day comes that Foodidle isn't
    cutting it they'll return for the answer, a more knowledgeable and
    informed user. In the mean time we let them get back to work with
    one less problem to solve.
4.  **Mixed Media keeps people engaged -**Many applications will kick
    off documentation with a screen cast and a voice over. These are
    great cause you get to see how the developer thinks the product
    should be used. Then, you never see another screen cast again.
    That's a real shame, cause if ever you wanted to watch someone go
    through an example, it's on the really complex stuff. It's easy to
    lose focus when faced with a wall of text, so throw in some videos,
    pictures, screen captures, etc. to keep people stimulated.
    Regardless of how you feel about [Why's Poignant Guide to
    Ruby](http://mislav.uniqpath.com/poignant-guide/book/), the one
    thing it isn't is boring. How many people have read through that
    documentation just cause they wanted to see what would happen next?
5.  **The final section should really just point to more dynamic
    documentation -**Remember the limited resource analogy? If it's
    really true then we have to assume that not every subject is going
    to be adequately covered. So let's make the last few sections point
    to other sources of documentation. These include (but are not
    limited to) an example of how a power user is doing things, blog
    posts, email lists, a change log of updates to the documentation, a
    weekly podcast, etc. All of these other avenues give people another
    chance to get their problems solved, while keeping the monotony of
    writing documentation low for the team.

Staying motivated is the hardest part
-------------------------------------

The worst documentation is the one you never write, so do what you can
to keep the process fresh and engaging. If writing long form
documentation is getting you down, then try something novel like a
screencast, or a blog post. If a user has explained something really
well on the forums add their comments to the "official documentation"
and give them a big thank you. Do what you can to make documentation fun
for the team as well as the users and you'll be rewarded with less
frustration on both ends. When you write documentation that explains how
to get work done, your users will respond appropriately. Everyone likes
it when work comes easy.
