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

The key idea is *switching*. An electrical switch is a device that can be used to 'turn' a circuit on or off. You use switches every day: for example, to turn the lights on or off in your room. More precisely, an electrical switch controls the flow of electricity: electricity can flow through a switch when the switch is on, but not while the switch is off.

How might switching be useful for doing calculations on numbers? It's easier to see if you count using *binary* numbering. In everyday situations, you use a numbering system with 10 digits: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$ and $9$; when you need to go higher than 9, you start using multiple digits: $10$, $11$, $12$ and so on. In binary, there are only two digits &mdash; $0$ and $1$. To go higher, you have to go up to multiple digits faster. So, to count in binary, you would write: $1$ ("one"), $10$ (pronounced "two"), $11$ ("three"), $100$ ("four"), $101$ ("five") and so on. We'll circle back to this later, so don't worry if this doesn't make sense quite yet.

Binary is useful for representing numbers in circuits because each binary digit has only two possible values: $0$ or $1$. This lines up nicely with electric switches, which also have two possible states: on or off. So we represent numbers by letting "switched on" (electricity flowing) mean a binary $1$, and "switched off" (no electricity) mean a binary $0$.

Now for the tricky part! Buckle in and get ready:

The last key insight we need is that we should drive these switches *electronically*. A conventional switch is mechnical: you flip a lever or push a rocker to physically connect or disconnect a circuit. We're going to need a switch that is driven *electronically*: the input ('source') and output ('drain') are always connected, but electricity only passes through if there's electricity passing through a third 'gate' wire.

To spell it out a bit better: if there's power going through this 'gate,' then power can pass through from the source to the drain, like a switch that has been turned on. Similarly, when there's no power going through the 'gate,' then electricity entering the source line is blocked from passing through out the drain line; the result is like a switch that has been switched off.

As weird as these things might sound, they turn out to be pretty useful! In theory, we can interconnect a bunch of these switches strategically to build sub circuits that calculate things like the sum, difference and product of two binary numbers. In fact, we'll figure out how to do exactly that in the next chapter of this book.

In modern computers, we use something called a 'transistor' as this electronically-driven switch. Like we just described, transistors have three terminals: source, drain and gate. Transistors work like electronic valves: the more electricity that passes through the gate, the more electricity is allowed to pass from source to drain. Although transistors thus allow you to continually vary the source $\rightarrow$ drain current based on the gate current, we're only interested in using transistors as switches, so we're always going to either set the gate current to zero (or as close to zero as we can), or some other non-zero value. The former switches the transistor off (binary $0$) and the latter switches the transistor on (binary $1$).

We'll see later how you build circuits of transistors to implement calculations on binary numbers. For now, just keep in mind that the circuitry inside your computer switches transistors on and off to represent binary numbers, and interconnecting these transistors in a clever way causes the circuit to perform math on binary numbers. Wow!

## Programmability

Okay, so we have a rough idea how to build an electronic calculator. A computer is a programmable calculator, so next we'll need to take a look at programmability.

Our first question is: what should a program look like?

> Idea: a program is a sequence of instructions. An inst is a number - which op
>
> Idea: subcircuits for each operation. We know how to do this from the previous section.
>
> We also need a way to pick which subcircuit to run. Actually, turning circuits on and off is hard. It'd be easier to always run every subcircuit, but only pick the output for the operation we want. Multiplexers. Another thing we can build with transistors.
>
> We need somewhere to store the program. There's plenty of options: a ROM (yet another thing you can build with transistors), or maybe use real physical switches. Punch cards. What have you.
>
> Our programs are inherently sequential, but so far our circuits have been totally in parallel. How do you execute a sequence of instructions? 
>
> Idea: a clock for creating sequences. Rising and falling edges. 
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

> All up review. This is the von Neumann architecture and all conventional hardware uses it today

## Peripherals

> This computer is still not very useful. No way to get data in or out
>
> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.



> Congratulations on completing your whirlwind tour of how computers work. We're not out of the woods yet though. Over the next couple chapters, we'll take a deeper look at how you construct an electrical circuit to implement a von Neumann computing architecture and design programs for it.