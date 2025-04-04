---
layout: post
title:  I like Java 8 streams
date:   2014-04-22 21:38 +0200
categories: java code
---
I'm learning the JDK 8 API.  
This seems pretty sweet, for Java standards:

    Stream<String> input = Stream.of("Tick", "Trick", "Track");
    Map output = input.collect(toMap(t -> t.length(), t -> t, (t, t2) -> t + "," + t2));
    System.out.println(output);

Result: `{4=Tick, 5=Trick,Track}`

