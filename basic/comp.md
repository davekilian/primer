---
layout: chapter
title: A Basic Sketch&#58; Computing
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



> Walk through the steps of an instruction
