---
layout: chapter
title: A First Sketch&#58; Booting
---

We've covered so much ground in this chapter! Let's review what we know so far:

First, we decided a computer is a *programmable calculator*. That means the computer can do calculations on numbers, but instead of providing direct access to the calculator, you instead provide a *program*. In our case, the program is a sequence of instructions, each of which specifies a single calculation to perform.

Next we thought a little about how to implement this in hardware. We decided to use networks of transistors, which we use as electronically-operated switches. We chose to represent all our numbers in binary, because then each digit has two possible values &mdash; $0$ or $1$ &mdash; corresponding to the two possible states of a transistor-based 'switch' &mdash; on or off. We thought a little bit about what we wanted to build out of transistors: subcircuits that run calculations on binary numbers, and subcircuits that store binary numbers, which we decided to call *registers*.

Then we added memory: a large array for storing binary numbers temporarily. This was to allow programs free up registers, since we only can afford the space to give ourselves a handful of registers. We also realized that memory is a great place to store our program itself, as a sequence of instructions, where each instruction is represented using a binary number. We figured we'd use two special registers to manage program execution: one to track the memory address of the next instruction to execute, and one to track the binary value of the instruction currently being decoded for execution. Those were called the *instruction pointer* and the *instruction register*, respectively.

In doing this, we realized we had arrived at a classic result: we had designed a computer that uses the *Von Neumann architecture*. All the important aspects of the Von Neumann architecture were already captured above!

Finally, we realized we had a fully working computer, but it wasn't very useful, because there's no connection between the computer itself and the outside world: no way to enter a program, no way to enter data, no way to get results out, and no way to hook up the computer to other computers. We decided to find a way to add "peripheral" devices to the computer to do all of this stuff.

Whew, talk about a lot! Thank you for sticking it out this far! We just have one more question to answer about our computer design ... how do we get everything started?

## Genesis

Memory is an electronic circuit that stores data temporarily: when you turn off the computer, all contents of memory are lost: with no power in the circuit, each binary digit in memory 'automatically' becomes a zero. So when you turn on the computer, every digit of every binary number in memory is $0$.

But wait &mdash; we said that programs are stored in memory. If we want our computer to do stuff, we need to get code into memory somehow. But we have a chicken-and-egg problem: if there's no code in memory already, how to we put code in memory?

The process by which a computer solves this problem is called *booting*. The term "booting" is short for "bootstrapping," which is in turn short for "pulling yourself up by your own bootstraps" &mdash; a very old saying that originally referred to an impossible task (it's physically impossible to pull yourself up by your own shoelaces!) but changed over time to mean bulding yourself something out of nothing (pulling yourself up without support). When a computer boots, we need to make something happen &mdash; program execution &mdash; out of nothing &mdash; the initial state of the computer memory is a big fat binary $0$.

To make this work, we'll need *firmware*: a built-in program that runs when the computer first turns on.

The name "firmware" is supposed to be a little bit of a joke! The circuitry that makes up the computer &mdash; including the calculator, the registers, memory, peripherals and so on &mdash; are often called "hardware," and the program that this hardware executes is often called "software." When we boot the computer, we run a small software program that's innately tied to the hardware: hard-software, or "firwmare." Har har!

How do we make this work? What happens when you turn on the computer? We won't cover this in great detail until later in the book, but here's the high-level sketch.

Well, first we need a program to serve as our firwmare. The only purpose of this firmware program will be to locate a user-defined program, load it into memory, and start executing it. The firmware program will be tied to the computer itself, so it can make assumptions about the computer's hardware if need be.

Second, we need to store it somewhere. Remember it can't be in RAM (memory), because memory is ephemeral &mdash; that is, turning off your computer erases your computer's memory. We need to store our firmware program in "non-volatile" RAM, or NVRAM: something that behaves like RAM, but is persistent across computer poweroffs. This is usually a small chip inside your computer, next to your RAM.

Finally, we need a hardware process for loading the firmware code on boot. We'll talk about that later in the book.

And voila: a strategy for booting!

## Something Ends, Something Begins

Congratulations on completing your whirlwind tour of how computers work. We're not out of the woods yet though. Over the next couple chapters, we'll take a deeper look at how you construct an electrical circuit to implement a von Neumann computing architecture and design programs for it.