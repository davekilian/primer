---
layout: chapter
title: A Basic Sketch&#58; Programmability
---

To make our calculator programmable, we first have to answer a more basic question: what does a program even look like, anyways?

We need to make a tradeoff: on one hand, we want it to be relatively easy for humans to construct and understand programs. At the same time, we also want to make it straightforward to execute these programs with electronic circuitry. Those two goals are somewhat at odds! How do we strike a good balance between human understanding and execution in circuitry?

The time-old answer to this dillemma is a programming primitive called the *instruction*. Here's how it works:

An instruction has a human meaning: it's a command, like "set the current value to 6 ($0110$)" or "add 4 ($0100$​) to the current value."Each instruction can be represented as a binary number: that's how we represent the instruction in circuitry. As part of designing our computer, we'll define one kind of instruction for each function we built into our calculator; that's how programs will be able to access each function we built into our calculator.

Here's a table of imaginary instructions, where each of the instructions corresponds to one of the functions we used on the quadratic formula in the previous chapter:

> TODO a table of the calculator functions from the previous chapter. Headings: instruction name, definition (copied from the previous chapter) and numerical value

A program, then, can just be an ordered list of instructions. For example, here's our quadratic equation program from the previous chapter, rewritten to use the instructions defined above:

> TODO another table. On the left is each line from the 'program' listing in the previous chapter. In the right column is the binary representation of that instruction

To execute programs like this one, we will need to build a circuit that walks through the program one instruction at a time. For each instruction, this circuit will need to determine which calculator function the instruction designates, and activate the corresponding calculator subcircuit. 

> Animated schematic of an arrow walking through a list of instructions, and activating a corresponding subcircuit for each

So far, all of our instructions have been referring to a 'current value.' What do we mean by that?

In a computer, intermediate values that we are working on are stored in a subcircuit called a *register*. A register is just another network of interconnected transistors, except this network is designed to store binary numbers rather than operate on them. We use registers in our computer whenever we want to remember a binary number so it can be retrieved later. The act of changing the number a register holds is called a *store* or a *write*; the act of retrieving the number from the register is called a *load* or a *read*.

> ### What's in a Name?
>
> You might wonder where the name "register" comes from. The answer is not entirely obvious, and there doesn't appear to be a definitive point in history at which the word came into use.
>
> Historically, though, the word "register" meant something like "record." For example, cash registers record how much cash the business has received, and many local newspapers are called, "The &lt;Some Place&gt; Register." In a circuit, registers are involved in recording numbers, which might be why the word "register" was chosen for these subcircuits.

A computer will typically have a handful of registers, allowing the computer to track intermediate values that a program is currently working on. On such a computer, instructions are often expressed in terms of the registers they operate on; for example, `load A 6` might be human-readable shorthand for an instruction saying "store the binary value of 6 ($110$) in register $A$," and `add A B` might be shorthand for "load the values of registers $A$ and $B$, sum them, and store the result in register $A$."

I'm sure you're getting tired of me saying it, but: we will see how to implement a register as a transistor network later in this book :-)

So what did we decide about programs and programmability?

* A program is an ordered **list of instructions**
* Instructions are **commands with a human meaning**
* Instructions have **binary representations** for use in circuitry
* Computers execute programs **one instruction at a time**
* Intermediate values are **stored in registers**

Our basic sketch of a simplistic computer is starting to take form, but we're not quite done with it yet. Let's take a look at memory and data storage.
