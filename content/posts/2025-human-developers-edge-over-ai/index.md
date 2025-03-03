---
title: Uncovering Human Developers Major Edge over AI
description: I demonstrate one Major area where Humans Developers can Outsmart the AI, albeit even here it should be Collaborative Effort!
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: false
date: 2025-02-25T11:11:11+00:00
url: /2025/human-developers-edge-over-ai/
tags:
  - AI
  - Agents
  - Programming
  - Software Architecture
  - Hyperscalers

---

## Overview

As a continuation of my [Programming Revolution](/2025/the-next-programming-revolution/) series, today we explore one major area where Human Developers can still outperform the AI (IMHO)! Though, I believe this should be very much a collaborative effort due to AI's ability to analyze vast amount of data (including sources) and find common concepts and ideas.

## Technical Debt

By now we probably all were wowed by latest GPTs ability to generate large amount of code from prompts. Beyond the Very common presence of mistakes in the generated code, the big issue in my view is the level of abstraction. In a way we are losing information here, the original prompt of What we wanted to Build is seldom captured, even if generated code is used. 

In other words - consider that generated AI code is very platform/language/framework specific, which itself is Bound to become obsolete in the future. However the original Intention, essentially the AI Prompt, is critical as it captures the core business/functional need!

## Elephant in the Room

Another critical aspect of the solution is performance. While the cloud offers the promise of "hyper" scalability, it also introduces significant overhead due to the isolation and context-switching of multiple cloud tenants. Additionally, virtualization layers may be required to ensure compatibility between hardware and user-supplied software, further impacting efficiency. Moreover, runtime security is another key factor, inevitably adding to execution overhead.

Of course it doesn't mean we should eliminate security or virtualization, rather, the emphasis here is on the Lack of proper level of abstraction to make efficient use of underlying infrastructure.

## Abstraction and Configuration

Another example is the impressive innovation of GPU/TPU compute via their instruction set capable of SIMD (Single Instruction on Multi-Data). However, most of existing software written in imperative programming languages aren't able to take advantage of this without refactoring.

And what about cost? GPU/TPU is often more expensive and we may want to only utilize it for urgent workloads. How can we re-engineer our software dynamically based on whether we are running time-critical computation or non-essential report?

## Aspects - Both Declarative and Imperative

After years of evolution in Computer Science the leading approaches are Imperative, Declarative and Aspect-Oriented programming paradigms. What I argue is that we need a brand new AI-paradigm, with completely new levels of abstraction.

In a way, perhaps best to think of it as educating a child. We often teach basic skills of writing/reading, or communication, and then build on top with trade-specific training often sprinkled in with constraints.

For example - imagine simply giving AI instructions: Here is how you calculate AR/AP, and here is the catalog of items for sale (and inventory, and orders, payments, etc). Perhaps we then would sprinkle in Constraint rules with priorities, such as "Stay cost-effective", and "Ensure RBAC access" and "Encrypt all data in transit and at rest". And that is it, we don't need to worry about writing manually endless lines of imperative instructions!

## Summary

Wait, but what about Humans? How are we essential here?

Today AI is is far from being able to act as I described above. This is where I believe humans are essential, to generalize and rethink our Abstractions in such a way as to reframe available services. We'd need to re-examine how we compose imperative code altogether - with technologies such as JIT (just in time compilation) we have the ability to streamline execution even of different tenants, as long as security posture allows it.

To use real-world example: the innovative eBPF design - allowing specific safe subset of instructions to execute efficiently in OS kernel space - unlocked a world of possibilities for efficient monitoring, debugging and much more!

Thus by keeping abstraction levels clearly defined and familiar for AI Agents, we could achieve efficient execution and even will be able to cleanly introduce new capabilities in the future, or optimize existing capabilities without having a legion of developers for refactoring the code.

## Parts 1 and 3 of this series

- [The Next Programming Revolution](/2025/the-next-programming-revolution/)
- [Introducing Merka Cloud](/2025/introducing-merka-cloud/)

## Some further reading to explore

- [Cloud Architecture Will Fail You, Distributed App Architecture Will Not](https://akka.io/blog/cloud-architecture-will-fail-you-distributed-app-architecture-will-not)
- [Software Engineering At Google - Lessons ans Book Link](https://swizec.com/blog/what-i-learned-from-software-engineering-at-google/)
- [Security Challenges and Complexities of Cloud GPU by Fly.IO team](https://fly.io/blog/wrong-about-gpu/)
- [High Performance Concurrency by Martin Fowler](https://martinfowler.com/articles/lmax.html)

![Same Prompt - lovely image yet a bit Creepy, No?](Fj14IJIptFbqr8GZgXQG--2--a0mbr.jpg "AI and Human collaborating on source code")

{{< alert "image" >}}
**Images By Flux Schnell via Nightcafe**
{{< /alert >}}
>> Prompt: Use mostly Fuchsia color pallet. Beautiful geeky female engineer with large glasses along with manly AI robot looking at complex source code on a large screen. They seem to be debating something on screen while engineer is near keyboard ready to type. Futuristic style furniture and home in the background.
