---
layout: post
title: SRE vs. DevOps
categories:
- sre
date: 2020-03-21 14:57 -0400
---
I don't think I've ever fully understood the "DevOps" role and its relationship with SRE. I knew they were somewhat related, but perhaps since I wasn't in the industry when DevOps was at its peak, I don't think I could specify the differences. Mike Doherty (Google SRE) outlined this problem quite well:

> Site Reliability Engineering: we don't know what DevOps is, but we know we're something slightly different.

Recently I've become more aware of my knowledge gap in this area, as I've interviewed quite a few "DevOps Engineers" for an SRE role. The more people I interview (I've conducted around 20 interviews in the past few months, with no prior interviewing experience before that), the more clear the distinction has become, but I still couldn't put my finger on the fundamental differences. Here are a few things I noticed (of course, any generalization will have its outliers, but in general this is what I noticed):

- DevOps engineers described their experience in terms of the tools and technologies they used, whereas SREs described the problems they solved and how they solved them
    - "Created CI/CD pipelines using Jenkins and Ansible playbooks" vs. "Automated a previously manual process, decreasing deployment time by x hours / month"
- When given hypothetical situations, DevOps engineers pointed out aspects of their philosophy that helped in that situation, whereas SREs dug into the specific situations
    - "Infrastructure as Code helps with this" vs. "How many regions do we need this in, what is the usage across the different regions?"

Today while reading [Seeking SRE](https://www.amazon.com/Seeking-SRE-Conversations-Running-Production/dp/1491978864) (from which the Mike Doherty quote above is also pulled), I found this analysis by Thomas Limoncelli (Stack Overflow), which really clicked for me (emphasis mine):

> If you look at job advertisements the answer is quire clear: the industry has decided that DevOps engineers focus on the Software Developement Life Cycle (SDLC) pipeline with occasional responsibilities for production operations. Job advertisements for SREs focus on production operations with occasional responsibilities for the SDLC pipeline.The two are the same thing: the difference is in emphasis. . . Once CI/CD enables rapid releases, the focus changes to production operations and likewise job titles often change to SRE.

This analysis is accompanied by a diagram similar to the following:

![limoncelli model](https://www.shaunabram.com/wp-content/uploads/2019/03/SRE_DevOps_Diagram-1.png "The Limoncelli Model of SRE, DevOps and Agile strategies")

As I now understand it, DevOps was a response to increased development velocity (caused by Agile, etc.). With the development bottleneck removed, the next bottleneck was in testing and deployment -- and the solution to this problem was DevOps. DevOps engineers (rightly, in their case) focused on that bottleneck, and developed tools and philosophies to increase deployment velocity.

Just like DevOps was a response to the success of Agile and other development philosophies, SRE seems to be a response to the success of DevOps in removing the bottleneck from the deployment pipeline. With that bottleneck removed, it became clear that the new bottleneck was in actually running and managing the production systems reliably. Increased deployment velocity highlighted many issues in production operations, including scale issues, monitoring, cost, toil, etc. So SREs (rightly, in their case) focus on the overall reliablility of the production systems, reaching back to CI/CD and testing when necessary to improve the system as a whole.

I think the Limoncelli model shows quite clearly the difference in focus I've been seeing when interviewing DevOps engineers. Even though we use many of the same tools and have similar goals, we operate at different levels, and it's a fundamental change moving from one role to the other.

I think this resolves my knowledge gap I outlined above, but it brings up an interesting question: if DevOps was a response to the success of Agile, and SRE was a response to the success of DevOps, what will be the response to the success of SRE? Where will the next bottleneck be, and what fundamentally new philosophy will arise in response?
