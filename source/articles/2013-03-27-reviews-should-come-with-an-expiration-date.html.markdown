--- 
title: "Reviews Should Come with an Expiration Date"
description: "Why would I care about a review for an App that's been updated 40 times since the reviewer gave feedback? I wouldn't."
date: 2013-03-27
popular: false
published: true
tags: reviews, product management, cats
---

Let's "imagine" for a moment that you are a huge fan of cats. Not the adorable creatures that live in your house and destroy your furniture, but the [terrifying Broadway musical](http://www.amazon.com/gp/product/B00004XMTJ/ref=as_li_ss_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B00004XMTJ&linkCode=as2&tag=wwwandytroutm-20). Now imagine your delight when you hear that a new mobile game is coming out, based on the magical world of the cats musical. You quickly hit up your app store of choice, ready to get in and mix it up with Rum Tum Tugger himself, but sadly you discover that the game isn't getting the reviews you had hoped for. Turns out it's a bit buggy, and the controls have a few quirks, and so people are shying away from a recommendation. Although Cats is your favorite musical ever, you're also a feline on a budged, so you decide that you'll keep your 2.99 for now.

Time passes, and as fate would have it you bump into a fellow cat fan on the bus who is LOVING this awesome Cats:The Broadway musical:The game that they just downloaded. And you must agree, it looks great! None of the original complaints seem to be an issue with this game... what gives? You rush to the app store, and again you discover that the game has an average score of 2 out of 5 stars... can you trust it?

No. You can't trust the review, and that's really the problem. Many review systems still look like they did almost 2 decades ago when the things being sold online came from *traditional retail* - that slow lumbering beast. And so, an average rating seems reasonable. After all, how much does a vacuum cleaner change from one version to the next? Probably not at all. 

But vacuums aren't the only thing being sold online anymore (gasp!). Now we're selling digital products, and digital products **change all the time**. We all read [The Lean Startup](http://www.amazon.com/gp/product/0307887898/ref=as_li_ss_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=0307887898&linkCode=as2&tag=wwwandytroutm-20) so we're getting products out the door early! Agile isn't just for grumpy software managers anymore, we're all trying to iterate quickly, let the customer guide the product, and move on to greater things. 

But iterating quickly means you need to be able to recover from mistakes. That becomes difficult when you're judged on the sins of the past, which is exactly what an "average rating" system captures. It's actually even worse than that - many new apps get a surge of reviews when they first launch, and that seed of reviews can haunt or reward them far into the future of the product. It takes a lot of convincing to get someone to try a product that's recieved 50 2 star reviews, even if you did take the feedback and make it better. 

I can hear some of you saying "don't release crap and it shouldn't be a problem!", but that's not the whole story. Yes, even when releasing a minimal product the *quality* has to be there, and then you can grow the feature set. But there are many app reviewers who don't rate a product on what it is, but against what its competitors are. Releasing the minimal feature set still means 2 and 3 star reviews with comments like "Wanted to like this, but, it's missing foobar integration which Whizbang's product has had *forever*. That's a great review to get because the customer shared some important data with you- They care about foobar integration. You just got your first customer feature request and it's pretty easy to add. So you do so, and you push a new version of your app... and your average rating doesn't change at all. Why? Because that customer has already left, and they're not going to come back until they start hearing some good things about your app, until you *fix some of the problems* and they see a better app score. 

Now you're in this weird catch-22 situation where the best target audience for your app came and left you feedback to improve, and so you did, but they won't give you a second chance until they see your rating improve, which it won't unless they come back and try out the new features and give you a good rating. The problem is that we're using a rating system that was designed for vacuum cleaners, and we're applying it to little pieces of software that can change literally every day. We need a new way of rating and measuring improvement that reflects this rapid rate of change. 

## You want me to propose a poorly thought out solution? OK!

I'm actually a little hesitant to propose a solution, because I think there's a lot of ways to slice up the problem, and what I'll end up with is something too complicated for the average shopper. For all the faults of the 5 star rating system, its enduring quality is how dead simple it is to understand. More stars, more better! What could be simpler? So you could just reset the star rating when a new version is cut, but that's too far in the other direction - you'll be constantly looking at apps with 0 or 1 reviews, and for all the faults of using old reviews for a rapidly iterating product, there is still good data among the bad. 

The engineer in me wants a graph of review history over time, because it's a graph! and that's really all I ever want to look at. It would even have vertical labels to indicate where a new version was cut! 

What a nightmare that would be for the average shopper. Grandpa has a hard enough time with his new phone... I'm pretty sure extra graphs isn't going to make that better for him, even though I would love it. Drilling down into this kinda of data is equally useless - people want an easy way to thumb down a page of options on the bus, and if it's much more complicated than star ratings you're doomed. 

So let's stick with stars, but how about a rolling average? Let's look at the past 10%? 20%? 50%? of reviews for the app, and let's also include a symbol to indicate how fresh the updates are (maybe a rotting apple... people love rotting fruit!). I think that would have a couple desirable effects:

1. It would still encourage app developers to release functionality often, because there isn't an advantage to waiting. If the feature is good, then it will have a much higher impact on your average rating.
2. Reviews are more immediately meaningful, and that translates into more people feeling empowered to give a review. 
3. Freshness helps customers decide if this was a great app 3 years ago that's getting by on its initial buzz, or a great app now with active development.
4. Rotting. Apples. 

That's about as good as I can come up with, but then again my data visualization skills top out at the flowchart. Maybe you can do better? Let's fix this. We want people to get their ideas into the marketplace early, but the existing review system creates a perverse incentive to hold out for a big bang of positive early feedback, which, if you don't get, encourages you to create abandonware and move on to the next idea. I don't want my app store clogged with dying good ideas, it makes me sad. 
