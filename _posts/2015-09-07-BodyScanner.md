---
layout: post
title:  Body-scanner estimation
date:   2015-09-07 22:48 +0200
categories: estimation agileundivided
---
9 out of 10 coaches agree: Estimating is not about the numbers, but about the dialogue.  
Even though, many teams find themselves discussing a meager difference in story points - often to the point of frustrated sighs - while the technical details are long clarified.

Today, I have been listening to an explanation of story point estimation. The team was just discussing a list of criteria to judge stories by, and I couldn't help but think: "What if we just cut to the dialogue instead of dealing with points, and used the criteria to encourage it?"

That thought led to a quasi-algorithmic way of estimating, quickly dubbed "Body scanner estimation" by my colleague [Ilja Preuß](https://twitter.com/ipreuss).

### How to play

1. Discussing the story itself, and answer any questions.
2. Answer all of the following questions with either Yes or No.
   * Inside/Outside
     * Do we need to pull support or input from outside the team?
     * Does it affect outside systems?
     * Do we need to share knowledge about the results?
     * Does it need management approval?
   * Knowledge/Skill
     * Does it need specialized knowledge? (Or can any of us do it?)
     * Is this story the first of its kind for our team?
     * Is it very time consuming?
     * Is it annoying to complete?
   * Technical
     * Do we have technical debt in the vincinity?
     * Does the change ripple throughout our system?
     * Do we need to set up testing infrastructure?
     * Do we need to set up build infrastructure?
3. Now, count the number of "Yes" and add 1 as the base cost.
4. Round the result to the nearest number from Fibonacci's sequence to get your estimation.
5. Sanity check the result.

This method of estimation gives teams a handrail to work with, with questions to spark further thought and discussion.

I yet to try Body scanner estimation, so I am eager to hear of your results. Do the questions make sense to you? Did you add some of your own?  
More importantly, though, did you come up with a fresh way of estimating lately? 
I'd love to hear from you.