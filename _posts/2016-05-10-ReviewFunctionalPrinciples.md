---
layout: post
title:  Review of "Functional Principles for Object-Oriented Development"
date:   2016-05-10 18:49 +0200
categories: code java software craftmanship
---
After a long time of agility and philosophy, here's something technical for a change.

### Previously...
Yesterday, I was talking OO and functional programming with Alex Chythlook, who told me that some problems I faced in Anathema could have been solved much easier applying functional programming idioms.  
When I asked for details, he pointed me to a [talk](https://www.youtube.com/watch?v=GpXsQ-NIKXY) Jessica Kerr (@jessitron) held at GOTO 2014.  
[Go here](http://www.slideshare.net/jessitron/functional-principles-for-oo-developers) in case you're watching the talk and would like to actually see the slides.  

### tl;dr:
All of her points are well made, and she's an entertaining presenter. I am happy that she pointed out some things that I didn't have names for previously.
However, I am surprised that many of these ideas are functional, as they just appear to be thorough applications of OO principles to me. If they have been functional all the time, then it is certainly good to call them thus.

### What stood out
"Errors are data too" Jessica said and told us to "not interrupt the execution flow".  
I've long spoken out against checked exceptions, and this nails it: If I treat an error as data, I am forced to deal with it. Right now, just where I would process the good result. No handing the exception outward, no wrap-to-catch-later.  
That way, Exceptions are limited to things that I, as a programmer, have not foreseen, and that's the way they are meant to be used.  

Idempotence, something she touches on in the very end, is quite important, too. Good to have a word, now. It describes the idea that an executable block of code (so, a function or a Single Abstract Method object) should change the world only once, even if it's called multiple times.  
From her talk, I picked up the notion that this should be true for every function, and I don't fully agree with that because complexity increases when I build things out of things that build things, even if those are just functions.  

The third main takeaway was her call for Lazy Evaluation. Doing that forces you to think in Objects or First Order Functions, and prevents procedural style – and that should always be a good thing.  

### What appears to be OO
I first stumbled when Jessica introduced a service object to limit a function's access to the database. Isn't that an application of the interface segregation principle (ISP) and the Single Responsibility Principle (SRP)?   
Smalltalk people always told me that even in Java, the client should define the exposed interface, and this is just that: If I need a service that just inserts, the method should have access to only that.  

Next, she speaks about specific typing - again, isn't that just OO? If something represents a name, I should call it "Name", not "String". The DDD people have said it since 2004 and hardly anyone listened, so Jeff Bay had to point it out again in his [paper on Object Calisthenics](https://www.cs.helsinki.fi/u/luontola/tdd-2009/ext/ObjectCalisthenics.pdf) some seven years ago, calling on us to "wrap all primitives and Strings" (and numeric objects, of course).  
Applying this principle in classes and productive code, I can well say that it is a game changer - your code becomes much more clear and expressive this way, even more so when you apply his next rule – "use first order collections" - as well.  
Back to Jessica: Good on her picking up on that, I fully agree. It surprised me, though, that she watered down the principle by us to Options and Tuples later on in her talk. Those two are never domain specific, so effectively, she just put two new primitive types on our plate.   
More recent languages have more elegant ways of expressing these concepts, and they might feel more at home there.  
I was surprised once more when she presented the lack of concern about when or how my code is executed as a principle of functional programming. With the OO concept of encapsulation comes the idea of Single Abstract Method objects, which are handed around as executable blocks. She even pointed us to the GoF patterns Command and Strategy, so clearly, this has been around for a while and was considered OO back then.   
Did the GoF silently sneak in functional ideas? How dare they!  

### What I didn't quite get
Apart from these three good points, there was one I didn't get: Structural Sharing? What was it about, memory efficiency? Didn't she just tell us that we should rely on our compilers instead of doing their work?

### Summary
So, all in all, it doesn't matter. Whether it's OO or functional, this is a good talk to watch. 
If you want to brush up on intermediate concepts of coding or see some examples of how things might get easier if you break your common patterns: Go watch!