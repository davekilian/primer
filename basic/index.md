---
layout: chapter
title: A Basic Computer
---

It is incredible to behold how fast and complex computer hardware has become since we first started building computers in earnest back in the 1940s-1950s.  [The power adapter for a modern MacBook Pro laptop includes its own onboard computer that is more powerful than the earliest Macintosh computers](https://www.ibtimes.com/your-macbook-power-adapter-has-more-powerful-processor-original-mac-2202242). For several decades, computer hardware has been improving at an exponential rate, roughly doubling in complexity every two years &mdash; the industry has managed to hit this number so consistently for such a long time that the phenomenon was even given a name: [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law).

In this chapter we will build ourselves a "minimum viable" computer. While this computer we will describe meets all reasonable definitions of the term "computer," and even resembles some of the first computers ever built, it will be a vast oversimplification of the computers we use today.

Before diving in, we'll do a short overview of binary number systems. Binary plays heavily into the design of computer hardware, because the two states are easy to represen using electronicst: 1 for the presence of charge/voltage, or 0 for the lack thereof.

With binary under our belts, we'll move onto the precursor to full computers: digital circuits. We'll cover the basic building blocks of circuits, and look at a few things you can do with circuits that don't amount to full computation. With that understanding, we'll be well-equipped to make our circuits programmable, turning our circuit into something like a computer. Then we'll add memory to our system, completing our computer in its most basic form.

Finally, we'll close out with a high-level sketch of how we'd add other key hardware to our system, such as disks for storing data persistently (not lost when the system is powered off and then on again), and peripherals so that humans can interact with the machine. 