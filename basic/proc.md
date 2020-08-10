---
layout: chapter
title: A Basic Computer&#58; Processors
---

> Picking up from where we left off previously, now we have a calculator, but you can only do one operation. What if I want to program a sequence of operation the calculator should do?
>
> This is probably a good time to cover the theoretical meaning of the term 'program' as a sequence of steps, and maybe show a couple of examples
>
> Build a toy instruction set
>
> Build a ROM we can use to store the sequence of instructions (a program)
>
> Add a new fundamental circuit: a clock, which is just a timed circuit that sits in front of the power source and turns the power on and off at a regular rate.
>
> Idea: each time the clock "ticks," move to the next instruction in the sequence.
>
> How fast can the clock tick? It depends on the propagation delay of the longest line in the circuit. We need to be sure everything has 'settled' for the current instruction before moving onto the next instruction
>
> Now step back - what we just built is the core component of any computer: the processor.
>
> A processor is a hardware interpreter for a programming language. Typically, the hardware and the programming language are co-designed, such that the language is simple to implement in hardware. Like we did above, the typical pattern is to
>
> * Build a set of logic circuits that accomplish basic tasks: adding two numbers, multiplying two numbers, etc. 
> * Wire up all these circuits to a multiplexer
> * Represent a program as a sequence of **opcodes** or **instructions** which each correspond to one of these subcircuits
> * Feed the current instruction into that multiplexer to select which subcircuit to read
> * Use a clock and a program counter to demultiplex the opcodes one by one sequentially
>
> Now we have a processor, which is basically a programmable calculator, which runs through a predefined sequence of calculations one by one, updating a set of binary numbers. But because the program is stored in read-only memory, our calculator still isn't really programmable, so by itself, a processor is not fully a computer. So let's take a look at the last major component we need: writable memory.