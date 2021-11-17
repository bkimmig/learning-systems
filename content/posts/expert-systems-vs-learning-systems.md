---
title: "Expert Systems vs. Learning Systems"
date: 2021-11-05T:00
authors: ["Jovan Sardinha"]
---

I think what we've and others have shown over the last years is how surprisingly useful they can be and how powerful quite a simple idea can end up being. So I'm just going to talk about the beginning with framing you know.

I've always thought about AI as if effectively bifurcating into two different types of approaches.  This is when we think about AI in the history of AI.  On the one hand you know we can try to build expert systems that rely on hard-coded knowledge that basically are hand crafted with the solution to a problem. They're usually inspired by logic systems and mathematics. For a long time was the way that most people attempted to build AI. The problem is that those kinds of systems can't deal with the unexpected.  They basically usually fail catastrophically if something hasn't already been programmed into them - if they encounter something unusual or that the programmer had not foreseen. The other interesting issue is that of course they're limited in scope to the sorts of solutions that we are able to articulate.

I think why this is such an exciting moment in scientific history and while you're here is that there's been this sort of big Renaissance if you like or of the learning system approach. Here instead of programming solutions we and we build systems that are able to learn for themselves from raw data and learn their own solutions to problems. What we hope is that these systems will be sufficiently general they can generalize to all sorts of new tasks. Perhaps tasks they've never seen before and actually indeed even solve things that we as human scientists are not able to do. Maybe the promise of these systems is that they could go beyond what we able to solve on our own.  I'm going to talk about that in the in the latter part of this talk now officially in learning systems and why I think what CBMM is is doing is so great and also what we do at deep mind is that we can look to the best learning system we  - the brain (also effective companies) human brain and see if we can be inspired by understanding that better inspired about new algorithms that we could use new representations new architectures they're inspired by neuroscience and our understanding of the brain in complete though that is. I would say not only can we be inspired but we can also validate algorithms that we've come up with ourselves. If we get build a system like that reinforcement learning we can then see you know when we find that the brain implements a form of TD learning in some famous results in the 90s, we could be confident then that reinforcement learning and is plausibly part of a kind of overall AI solution. So we can push harder on those techniques if we know that the brain also uses those techniques. That point of validation is often overlooked but it's very important when you are running or in charge of a big engineering program you know where do you decide to put more effort in if something doesn't work which you know things often don't work first time or even many times in research and engineering how much more should you push that approach.

Many interseting issues:
* Dellusion and debugging
* Covering the knowledge searchspace
* Understanding the system and the ethics of the decision
* Types of creativity

The three key characteristics that lend themselves to learning-sysytems:
* Massive combinatorial search space
* Clear objective function (metric) to optimize/hill climb against
* A very controlled data loop OR a simulator

If these three things hold, then we can build a very effective learning system.
