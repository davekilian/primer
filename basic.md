---
layout: chapter
title: A Basic Computer
---

In the previous chapter, we learned a little about computers and programs. We decided that a computer is a *programmble calculator*, which means that you give a computer a program (which is just a sequence of calculations), and the computer *executes* the program by carrying out each step on its internal calculator.

Now, how would we build one of these things?

Answering that question turns out to be a little tricky, but not all that difficult. Although people sometimes point to computers as a pinnacle of humanity's technological achievement, the real achievement is in the nuts-and-bolts of designing and building computers. The high-level ideas are actually pretty simple, even if sometimes they're not obvious!

Since a computer is a programmable calculator, let's start with the calculator part:

## Calculation

How are we going to build a calculator out of electronic circuitry? This is probably the trickiest part of the whole design.

The key idea we'll use is *switching*. A switch is something you use to turn an electric circuit on or off &mdash; for example, you use switches every day when you turn the lights on and off in your room. More precisely, a switch controls the flow of electricity: when on, the switch completes a circuit and allows electricity to flow. When off, a switch interrupts the circuit, preventing electricity from continuing to flow.

How is switching useful for doing calculations on numbers? It's easier to see if you count using *binary* numbering. In binary, there are only two digits: $0$ and $1$. Just like with regular numbers, you use move to the next place when you run out of digits. The first few numbers look like this in binary:

​	$1$ ("one")<br>
​	$10$ ("two")<br>
​	$11$ ("three")<br>
​	$100$ ("four")<br>
​	$101$ ("five")

Binary is useful when paired with switching because there are only two digits &mdash; $0$ and $1$ &mdash; and a switch also only has two possible states &mdash; on and off. We can use "switched off" to represent $0$ and "switched on" to represent $1$ in a circuit.

That gets us closer: we know how to represent numbers in a circuit. But how would we do math on them? How would we add two numbers, for example?

One thing that might help here is to invent a new kind of switch. A conventional switch is mechnical. In between the *source* terminal (where electricity comes in) and the *drain* terminal (where electricity goes out), there will be a lever you can flip, a rocker you can push, or something else that physically connects or disconnects the terminals. Instead of mechanical control, we want electronic control. Say we add a third *gate* terminal: when this terminal is powered, the switch is 'on' and electricity flows from source to drain. But when the terminal is not powered on, the switch is 'off,' so electricity cannot flow from source to drain.

It turns out, if you have this kind of switch, you can build subcircuits that do some pretty interesting things. The basic idea is to have your input numbers go into a network of switches, which in turn switch other switches, and so on, until the output is something meaningful. For example, you might send the digits of two numbers into a network of switches, such that the 'output' of the switch network is each digit of the sum of those two input numbers. We don't have room to do it here, but in the next chapter we'll work out a few examples to give you an idea of how this works.

In modern computers, we use a device called a *transistor* as this switch. Technically, a transistor is more powerful than a simple switch: a transistor works like a valve, continually varying the amount of power that passes from source to drain proportionally to the amount of power that's passing into the gate. However, in computers we're only interesting in switching things on and off, so we don't use this capability.

So, to summarize, how are we going to build our calculator? The basic principles are to represent numbers using binary, so that a switched-on connection is a binary $1$ and a switched-off connection is a binary $0$. Then we use networks of transistors to do math on these binary numbers. We'll see some examples of how this works in the next chapter!

## Programmability

Okay, so we have a rough idea how to build an electronic calculator. A computer is a programmable calculator, and we have a high-level sketch for the calculator. How do we make it programmable?

Actually, here's a better place to start: what should a program look like?

Designing a program that we can execute on an electronic circuit is a little tricky because we have to serve two masters: on one hand, we want it to be relatively easy for humans to construct and understand programs, but at the same time we also want to make it relatively simple to implement programs using electronic circuitry.

Here's a good idea that has been implemented many times: a program will be a sequence of *instructions*. An instruction has a human meaning: it's a command, like "add these two numbers" or "set this variable to zero." There's an instruction for each thing we want the computer to do on its internal calculator. Each instruction is *also* a binary number; that's the representation we'll use to implement the instruction with circuitry.

> Example: table with some example instructions and their example numerical values

Our basic strategy will be to have one subcircuit for each instruction (using what we learned about calculations above), and then use the current instruction to pick the appropriate subcircuit for the current instruction.

But of course, in order to pick the right subcircuit for the current instruction, we have to know what the current instruction is! Where are we storing that program anyways? For now, let's rely on a circuit called a [read-only memory](https://en.wikipedia.org/wiki/Read-only_memory) or "ROM." The ROM is just a circuit that stores each instruction as its binary numerical value. Our program ROM will be a circuit that accepts a single input number &mdash; the index of the instruction we're executing &mdash; and produces a single output number: the numerical value for that instruction.

Okay, so we have an idea of how to read an instruciton and execute it; but a program is a whole sequence of instructions, not just one. How do we execute the instructions one by one? We'll need a couple more tools:

The first thing we'll use is a circuit element called a *clock*. A clock can't be built 





> The first ingredient is a clock. This is just a switch that turns on and off at a predictable frequency. The basic strategy is for each clock cycle to execute one instruction. We want the clock to cycle as fast as possible, while still slow enough that there's enough time for electricity to finish moving throughout the entire circuit. [crystal oscillator](https://en.wikipedia.org/wiki/Crystal_oscillator)
>
> The second thing we need is a register: a transistor circuit that stores a number. TODO explain how we set the current value to the next value in time with the clock going up and down
>
> Putting these things together, what does our master circuit looks like? TODO we need a register for tracking the index of the current instruction: 0 for the first instruction, 1 for the second, 2 for the third and so on. 
>
> Registers aren't just useful for 
>
> I guess we need to say "ISA" somewhere. Can be here as we outro

## Memory

> What if we need even more space than we can put in a register?
>
> Idea: an array of 8-bit integers. Like ROM but you can modify it.
>
> Idea: hey, what if we moved the program into RAM?
>
> Problem: bootstrapping. Firmware puts something in RAM to execute on power on.

## Basic Computing

> All up review. This is the von Neumann architecture and all conventional hardware uses it today

## Peripherals

> This computer is still not very useful. No way to get data in or out
>
> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.



> Congratulations on completing your whirlwind tour of how computers work. We're not out of the woods yet though. Over the next couple chapters, we'll take a deeper look at how you construct an electrical circuit to implement a von Neumann computing architecture and design programs for it.