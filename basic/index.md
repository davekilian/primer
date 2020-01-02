---
layout: chapter
title: A Basic Computer
---

It is incredible to behold how fast and complex computer hardware has become since we first started building computers in earnest back in the 1940s-1950s.  [The power adapter for a modern MacBook Pro laptop includes its own onboard computer that is more powerful than the earliest Macintosh computers](https://www.ibtimes.com/your-macbook-power-adapter-has-more-powerful-processor-original-mac-2202242). For several decades, computer hardware has been improving at an exponential rate, roughly doubling in complexity every two years &mdash; the industry has managed to hit this number so consistently for such a long time that the phenomenon was even given a name: [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law).

In this chapter we will build ourselves a "minimum viable" computer. While this computer we will describe meets all reasonable definitions of the term "computer," and even resembles some of the first computers ever built, it will be a vast oversimplification of the computers we use today.

## Calculators and Computers

Once upon a time, computers weren't devices, they were people; "computer" was a job description, like "engineer" or "salesperson."

Before the advent of the digital computerfs we use today, academic, scientific and engineering insitutions  employed (human) computers to run computations on rote arithmetic. Each computer typically assigned a calculator (usually a kind of mechanical calculator called a [slide rule](https://en.wikipedia.org/wiki/Slide_rule)), and were asked to string together sequences of these calculations to compute something more interesting. For really big jobs, a single computation would be split across multiple (human) computers, and combined together at the end to yield the final result.

To take an example out of the 2016 film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures), NASA (finish me)

Since NASA likes to launch things in the air and thus deals in parabolas, let's take the quadratic equation as an example:

$\dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$

Say you're a computer for NASA being asked to solve the quadratic equation for the coefficients $A=5$, $B=3$, $C=3$: 

$\dfrac{-3 \pm \sqrt{3^2 - 4(5)(3)}}{2(5)}$

Say you have a calculator which can add, subtract, multiply, divide, square and take the square roots of numbers. How would you compute the results of this equation?

> Unroll into a sequence of calculations (actually, two of them, because of the $\pm$)

> The big reveal: the sequence of calculations is a **program**, and a computer is at heart a programmable calculator - instead of needing to pay someone to string together the calculations, you can feed in a program (a sequence of calculations) and a set of input variables, and the computer does all the work of running the calculations one by one until yielding the final result.

