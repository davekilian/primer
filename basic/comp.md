---
layout: chapter
title: A Basic Sketch&#58; Computing
---

It's been a long journey, this chapter. Thanks for sticking it out thus far! What we have now designed for ourselves is something called the **Von Neumann architecture**, named for John Von Neumann, who first described it in a paper on computing published in the 1940s. Here's what he described &mdash; a lot of this should be review!

> Schematic diagram using all the official terms discussed below

Von Neumann's computing architecture included a *processing unit* which provided support for calculation. Specifically, it consisted of two components:

* An *arithmetic logic unit* (ALU) consisting of a set of calculation subcircuits, based on transistors
* A bank of *processor registers* for storing intermediate values those calculations run on

The Von Neumann architecture also included a *control unit* to provide programmability. This included two key registers:

* An *instruction register*, which stores the binary representation of the instruction currently being executed
* An *instruction pointer* (sometimes called a *program counter*), whih is a register that stores the memory address of the next instruction to execute

Finally, the Von Neumann architecture included memory, as an array of binary numbers used to store both programs, as an ordered list of instructions, and data generated and being used by these programs.

How do all these pieces work together?

> Walk through the steps of an instruction
