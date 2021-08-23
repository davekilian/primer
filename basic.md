---
layout: chapter
title: A Basic Computer
---

In the previous chapter, we learned a little about computers and programs. We decided that a computer is a *programmble calculator*, which means that you give a computer a program (which is just a sequence of calculations), and the computer *executes* the program by carrying out each step on its internal calculator.

This is a book about how computers work, so the next logical question is: how do you build one of these things?

Answering that question turns out to be a little tricky, but actually not all that difficult. People sometimes point at computers as a pinnacle of humanity's technological achievement, but when it comes to designing one, the devil's in the details: although the nuts-and-bolts work of constructing a reliable, fast, power-efficient computer may be difficult, computers are still pretty simple at a high level. Knowing what we learned in the previous chapter and just a tiny bit about electronic circuitry, we can figure out how computers work from basic principles. Each idea is simple, even if not always entirely obvious.

Where should we start? If a computer is a programmable calculator, why not start with the calculator?

## Calculation

It turns out the first insight we need is also the trickiest: how are we going to build a calculator out of electronic circuitry?

>I started drafting below, but I don't like the exact flow. Here's what I'm thinking instead.
>
>First say it's all about *switching*. Introduce the idea of switching a circuit on / off to allow or halt the flow of electricity.
>
>Then introduce the idea of binary numbers. We like binary because each binary digit (bit) has two possible values: 0 and 1. These can easily correspond to 'switched off' (0) and 'switched on' (1).
>
>Next say you *could* program using switches directly (maybe even mention dip switches), but you'd need a lot of switches to do anything interesting, and you'd be fiddling with switches all the time. Couldn't we have the electricity itself run the switch?
>
>Come up with some kind of concrete example of what you could do with these switches. The NOT gate is something simple enough.
>
>Then finally say we can use transistors as these switches. Explain transistors are really like valves, in that they have a source, drain and gate, such that the amount of electricity that is 'allowed' to flow from source to drain is proportional to the amount of electricity flowing to the gate. If there is no gate current, nothing flows from source to drain, like a circuit that is switched off, i.e. a binary 0. If there is gate current, then current flows from source to drain, like a circuit that is siwtched on / a binary 1.
>
>In the next chapter of the book we'll build a working calculator out of transistors, but for now just keep the basic idea in mind.

---

The cornerstone of the modern computer is arguably a tiny circuit element called a transistor. In circuit design, a transistor is an element that acts like an electronic valve: a transistor has a 'source' where electricity comes in, a 'drain' where electricity goes out, and a 'gate' which controls the valve. Sending electricity along the 'gate' allows electricity to flow from the 'source' to the 'drain;' when there's no electricity flowing into the gate, no electricity can flow from the source to the drain.

Here's the basic idea for our calculator: we're going to hook up a bunch of transistors to one another, so that each transistor drains into the sources and/or gates of other transistors. We'll put the transistors together in such a way that it does something interesting &mdash; like add two numbers.

Of course, to do that, we need some way to represent numbers using electricity!

> Idea: binary: a switch has two states, on and off. A bit is 1 or 0.

## Programmability

> Next we need programmability
>
> Idea: a program is a sequence of instructions. An inst is a number - which op
>
> Idea: subcircuits for each operation. Multiplex the result
>
> We need somewhere to store the program. Use a ROM
>
> How do we execute a sequence of instructions?
>
> Idea: a clock for timing
>
> Idea: a register to track where in the sequence
>
> Registers also useful as scratch space. Let’s add some to our ISA.

## Memory

> What if we need even more space than we can put in a register?
>
> Idea: an array of 8-bit integers. Like ROM but you can modify it.
>
> Idea: hey, what if we moved the program into RAM?
>
> Problem: bootstrapping. Firmware puts something in RAM to execute on power on.

## Basic Computing

> All up review. This is the von Neumann arch and all hardware uses it today

## Peripherals

> This computer is still not very useful. No way to get data in or out
>
> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.