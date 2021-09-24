---
layout: chapter
title: A Basic Sketch&#58; Memory
---

So far, we've sketched out a programmable calculator. A computer is a programmable computer. So what we have so far is a computer, right? Technically, yes, it is! But the computer we've described so far is so primitive as to be effectively useless in practice. Let me convince you of why:

Think what it would be like to program a computer like the one we just designed. How much intermediate data does a program typically need to work on? For example, think about our quadratic formula program. As intermediate values, we needed:

* Three inputs: values for $A$, $B$ and $C$
* One thing we're currently calculating
* Five things we already calculated: $-B$, $B^2$, $4AC$, $2A$ and $\sqrt{B^2-4AC}$
* Two outputs (one for the $+$ side of $\pm$ and one for the $-$ side)

That's a total of 11 things we need to store in registers. Do we have 11 registers? On a modern computer, maybe &mdash; on an early computer, probably not! The circuitry for registers requires a lot of space and power relative to other parts of the computer, which makes it infeasible to have a lot of registers. Modern computing architectures usually give you about 16 registers to work with; early computers often had even fewer. What do we do when we run out of registers?

If this sounds contrived, keep in mind the quadratic formula example is a toy, and most programs act on way more data. For example, say you wanted to write a program that takes a year's worth of daily temperature measurements and calculates the average temperature for any date range during that year. Forget the average itself: where would you store those 365+ temperature measurements, if you only have 16 registers to work with?

Fundamentally, there's a relationship between computing and storage. If you have a computer that can do millions of calculations per second, you need it to be able to store millions of numbers to do those calculations on. It doesn't matter if you have a computer that can do a billion calculations per second if there are only ~10 numbers to work on: there's only so much useful work you can do on so few numbers. As such, fast computers require a lot of intermediate data, and vice versa.

That's why all computers &mdash; even the early ones &mdash; included some sort of **random-access memory** (sometimes shortened to **RAM** or just **memory**). Memory provides mass storage for data that isn't needed right now, but may be needed in the near future. In the quadratic formula example from the last chapter, that piece of paper where we were writing down intermediate results served a similar purpose to what memory serves in a modern computer.

Here's the idea: first, we build a small, cheap, low-power circuit that stores a single binary number. We'll see in a future chapter how to do that. Once we have this circuit, we'll make many, many copies of that circuit &mdash; modern computers have billions of copies of this circuit! &mdash; and then we'll arrange them all in a neat row, like this:

> Diagram

We'll assign each number an **address**, which is just a number that uniquely identifies one of the many copies of our number-storage circuit. For example, the first copy of our storage circuit will have address `0`, the second will have address `1`, and so on:

> Diagram

Finally, we'll provide instructions that allow programs to access memory. Fundamentally, we need two new instructions: a `store` instruction, which copies the number from a given register into memory at the given memory address; and a `load` instruction, which copies from a given memory address into a given register. Some computers instead provide a single `move` instruciton which can copy in either direction.

This scheme gives programmers a simple way to 'spill over' when you have more data than you can hold in a register. In the quadratic formula example, we could store the input numbers and all intermediate calculations in memory; in the average temperatures example, we could store the list of daily temperature readings in memory. We will need to copy numbers into registers in order to run calculations on those numbers, but anything we're not calculating right this instant stays in memory.

By happy accident, it also turns out that memory is the solution to a problem we didn't even realize we had yet! We know a program is a list of instructions, but where is the computer storing this list of instructions? Now that we have memory, there's a clear, obvious answer: store the program in memory!

In conclusion,

* Memory is an **array of numbers**
* Each number is identified by a **memory address**
* Memory stores **intermediate values** as well as **programs** themselves
