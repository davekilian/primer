---
layout: chapter
title: A Basic Sketch&#58; Memory
---

We have now sketched out a calculator and a way to program it. We said that a computer is a programmable calculator, so what we have now sketched out is a computer, right? Well, technically, yes &mdash; we already have all the necessary elements of a computer! Unfortunately, we're not done: the computer as described so far is so primitive as to be effectively useless in practice. Let me convince you of why:

Think what it would be like to program a computer like the one we just designed. How much intermediate data does a program typically need to work on? For example, think about our quadratic formula program. As intermediate values, we needed:

* Three inputs: values for $A$, $B$ and $C$
* One thing we're currently calculating
* Five things we already calculated: $-B$, $B^2$, $4AC$, $2A$ and $\sqrt{B^2-4AC}$
* Two outputs (one for the $+$ side of $\pm$ and one for the $-$ side)

That's a total of 11 things we need to store in registers. Do we have 11 registers? On a modern computer, probably &mdash; on an early computer, probably not! The circuitry for registers requires a lot of space and power relative to other parts of the computer, which makes it infeasible to have a large number of registers. Modern computing architectures usually give you about 2-3 dozen registers to work with, but even then, many of those registers have special purposes and are not interchangeable. Early computers had even fewer registers!

So, what do we do when we run out of registers?

If this sounds contrived, keep in mind the quadratic formula example is a toy, and most programs act on way more data. Let's say you wanted to write a program that takes a year's worth of daily temperature measurements and calculates the average temperature for any date range during that year. Forget the average itself: where would you store those 365+ temperature measurements, if you only have 16-32 registers to work with?

Fundamentally, there's a relationship between computing and storage. If you have a computer that can do millions of calculations per second, you need it to be able to store millions of numbers to run calculations on. It doesn't matter if you have a computer that can do a billion calculations per second if there are only ~10 numbers to work on: there's only so much useful work you can do on so few numbers. As such, fast computers require a lot of intermediate data, and vice versa.

That's why all computers &mdash; even the early ones &mdash; included some sort of **random-access memory** (sometimes shortened to **RAM** or just **memory**). Memory provides mass storage for data that isn't needed right now, but may be needed in the near future. Remember how, in the last chapter, we had a piece of paper to write down the intermediate results of our calculation? Memory serves a similar purpose in a modern computer.

Here's the idea: first, we build a small, cheap, low-power circuit that stores a single binary number. We'll see in a future chapter how to do that. Once we have this circuit, we'll make many, many copies of that circuit &mdash; modern computers have millions to billions of these copies! &mdash; and then we'll arrange them all in a neat row, like this:

> Diagram

We'll assign each number an **address**, which is just a number that uniquely identifies one of the many copies of our number-storage circuit. For example, the first copy of our storage circuit will have address `0`, the second will have address `1`, and so on:

> Diagram

Finally, we'll provide instructions that allow programs to access memory. Fundamentally, we need two new instructions: a `store` instruction, which copies the number from a given register into memory at the given memory address; and a `load` instruction, which copies from a given memory address into a given register. Some computers instead provide a single `move` instruciton which can copy in either direction.

This scheme gives programmers a simple way to 'spill over' when you have more data than you can hold in a register. In the quadratic formula example, we could store the input numbers and all intermediate calculations in memory; in the average temperatures example, we could store the list of daily temperature readings in memory. To *use* any of those numbers, we still have to read the value back from memory into a register before running any calculations on them; but anything we're not actively using right now can stay in memory, freeing up our precious few registers to do other stuff.

By happy accident, it also turns out that memory is the solution to a problem we didn't even realize we had yet! We know a program is a list of instructions, but where is the computer storing this list of instructions? Now that we have memory, there's a clear, obvious answer: store the program in memory! The computer will store the address of the next instruction in a register, and read the corresponding instructions from memory one at a time.

In conclusion,

* Memory is an **array of numbers**
* Each number is identified by a **memory address**
* Memory stores **intermediate values** as well as **programs** themselves
