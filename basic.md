---
layout: chapter
title: A Basic Computer
---

> First we need a calculator
>
> Idea: circuit made of transistors. Digital so transistors like switches
>
> Idea: binary: a switch has two states, on and off. A bit is 1 or 0
>
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
>
> What if we need even more space than we can put in a register?
>
> Idea: an array of 8-bit integers. Like ROM but you can modify it.
>
> Idea: hey, what if we moved the program into RAM?
>
> Problem: bootstrapping. Firmware puts something in RAM to execute on power on.
>
> All up review. This is the von Neumann arch and all hardware uses it today
>
> This computer is still not very useful. No way to get data in or out
>
> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.