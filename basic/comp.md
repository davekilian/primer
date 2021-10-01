---
layout: chapter
title: A First Sketch&#58; Computing
---

It's been a long journey, this chapter. Thanks for sticking it out thus far! What we have now designed for ourselves is something called the **Von Neumann architecture**, named for John Von Neumann, who first described it in a paper on computing published in the 1940s.

Let's see what he described in this paper. Even though a lot of the terms will be new, I think you'll find a lot of this is review!

> Schematic diagram using all the official terms discussed below

Von Neumann's computing architecture included a *processing unit* which was, essentially, a calculator. It consisted of two underlying components:

* An *arithmetic logic unit* (ALU) consisting of a set of calculation subcircuits
* A set of *processor registers* for storing intermediate values

Von Neumanns architecture also included a *control unit*, which wrapped the processing unit (calculator) to provide programmability. The control unit included two key registers:

* An *instruction register*, which stores the binary representation of the instruction currently being executed
* An *instruction pointer* (sometimes instead called a *program counter*), whih is a register that stores the memory address of the next instruction to execute

Finally, the Von Neumann architecture included *memory*, to store both programs, as an ordered list of instructions, and data generated and being used by these programs.

How do all these pieces work together?

Let's say we already have a program loaded into memory, and the instruction pointer register already stores the memory address of the next instruction to execute. What happens next?

First, the control unit does a memory read: it fetches the instruction at whatever memory address is stored in the instruction pointer register, and stores the resulting number in the instruction register. The value stored in the instruction pointer register is then incremented &mdash; that way, next time around, we'll move on to the program's next instruction.

Now that the instruction register is storing the next instruction to execute, we need to figure out what it says to do! The control unit now *decodes* the current instruction, figuring out which ALU function is being invoked, and which register(s) the instruction operates on. The results are then sent to the processing unit.

The processing unit now reads from whatever registers the instruction specified, and activates the appropriate subcircuit. If the instruction is a mathematical operation (like adding two numbers), the subcircuit is part of the ALU; if the instruction operates on memory, the appropriate operation is sent to memory.

Finally, if the instruction resulted in an output &mdash; for example, if the instruction was a mathematical operation, or a memory read &mdash; the corresponding value is sent to the appropriate register.

This completes the process; now that we've *retired* (finished executing) the current instruction, we begin the process all over again for the next instruction. A modern computer will repeat this process anywhere between millions of times to billions of times per second!

To make this all work, Von Neumann's architecture relies on a *clock*, which is an electronic signal that turns on and off at regular intervals. The rest of the computer uses the clock signal to synchronize the different steps of this process, so that only one step happens at a time. You can think of a computer as executing one instruction per on-off cycle of the clock. (That used to really be the case, but as we'll see much later in this book, the truth is much more complicated on modern computers!)

We now have the programmable core of a computer. Congratulations! We just have a few more perfunctory details to fill in.