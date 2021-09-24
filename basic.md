---
layout: chapter
title: A Basic Sketch
---

> TODO do we have enough content now that it makes sense to split out each heading into a separate page? I feel like this page is very long, but I also feel like the individual pages would end up being very short, so I dunno. I don't want to add fluff just to make the pages appropriately long ...

In the previous chapter, we learned a little about computers and programs. We decided that a computer is a *programmble calculator*, which means that you give a computer a *program* (which is just a sequence of calculations), and the computer *executes* the program by carrying out each step on its internal calculator.

Now, how does one go about building one of these things? In this chapter we will lay out a basic sketch of the path ahead of us. We'll figure out we need to do, and what problems we'll need to work out along the way. This will give us something of a map to follow over the next few chapters, over which we'll fill in the details.

If a computer is a programmable calculator, then we're going to need to work with numbers, right? Let's start there!

## Numbers

So, how are we going to work with numbers in electronic circuitry?

The key idea we'll use is *switching*. A switch turns an electric circuit on or off &mdash; for example, you probably use a light switch to turn the lights on or off at your place every day. More precisely, a switch controls the flow of electricity: when it's on, the switch *completes* a circuit so that electricity can flow through it. When it's off, a switch *interrupts* the circuit, preventing electricity from flowing on through the switch.

> Diagram

How is switching useful for doing calculations on numbers? It's easier to see if you count using *binary* numbering. In our regular numbering system, there are ten digits, $0$-$9$; in binary there are just two digits: $0$ and $1$. In our normal numbering system and in binary alike, you move to the next number place when you run out of digits in the current place. As such, the first few binary numbers look like this:

​	$1$ ("one")<br>
​	$10$ ("two")<br>
​	$11$ ("three")<br>
​	$100$ ("four")<br>
​	$101$ ("five")

If it's not immediately clear how binary works, don't worry: we'll take a closer look at binary soon. For now, it's important to know that any number can be represented in binary, and you only need two digits: $0$ and $1$.

Binary is useful when you're working with switches because binary only uses two digits &mdash; $0$ and $1$ &mdash; and a switch only has two states &mdash; on and off. That lets us use a switch to represent a binary digit: we can use "switched off" to represent $0$ and "switched on" to represent $1$ in circuitry. To represent a binary number with multiple digits, we use multiple switches; for example, if we wanted to represent a 4-digit binary number, we'd need to use 4 switches &mdash; one for each digit.

For example, let's say we wanted to represent the number 6 in binary. We'd start by counting to six in binary:

​	$1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"),  $101$ ("five"), $110$ ("six")

It looks like we need three digits, so we'll use three switches:

* The 1s place switch, which would be switched off (because the 1s place of $11\underline0$ is $0$)
* The 10s place switch, switched on (the 10s place of $1\underline10$ is $1$)
* The 100s place switch, swithced on (the 100s place of $\underline110$ is $1$)

In practice, you might want to be able to store much larger numbers; for example, with eight switches, you could store any number from 0 to 255. If we wanted to use those eight switches to store the number six ($110$), all we need to do is set the switches as described above, and then set all the remaining switches off. That is, the 1,000s place switch should be off (set to $0$), as should the 10,000s place, the 100,000s place, and so on. We might write the resulting configuration as $00000110$ to remind us of all those extra switches that are all turned off.

Hopefully that gives you a feel for how to represent numbers in binary using circuitry. If things still feel a little fuzzy, that's ok &mdash; remember we'll go in greater depth over the next chapter of this book.

## Calculation

Now we have an idea of how to represent a number in a circuit, so it's time to start thinking about the next step: how do we use circuitry to run calculations on binary numbers we're representing using switches? For example, how would we use switches to add two binary numbers?

To make this work, we need to build ourselves a new kind of switch.

A conventional switch is mechanical: in between the *source* terminal (where electricity is coming in) and the *drain* terminal (where electricity goes out), a switch will have some way to *mechanically* connect and disconnect the two terminals: it might be a lever you can flip, a rocker you can push, or something else.

> Some kind of diagram. Could be a schematic, or a cross-section of a real switch, or something.

To implement our calculator, we're going to want something slightly different: a switch that can be controlled *electronically*. Unlike the conventional kind of switch we just described, this new 'electronic' switch will have *three* terminals: the source and drain terminals like a conventional switch, plus a new terminal called the *gate.* The gate terminal is how we will operate the switch electronically: when we power the gate terminal, that completes the circuit, allowing electricity coming into the source terminal to flow out the drain terminal. When we power off the gate terminal, that interrupts the circuit, meaning electricity can no longer flow from source to drain:

> Add a basic schematic diagram

In modern digital circuits, always implement electronic switching using a circuit element called a *transistor*. We'll talk about transistors later on in the book.

Transistors are quite useful for implementing math on binary numbers! The basic idea is to represent each mathematical operation using a network of interconnected transistors. For example, say you want to build a subcircuit that adds two binary numbers: this subcircuit will have a set of "input" terminals for the digits of the binary numbers we want to add, as well as a set of "output" terminals with the digits of the resulting binary sum. In between those terminals will be a network of transistors, which mix the input signals as needed in order to obtain the correct output signals:

> Another diagram

We already have most of the tools needed to figure out how this network of transistors might look for a simple operation like binary addition, but it would take a lot of space to fully spell it out. For that reason, we'll wait to cover that until the next chapter.

With that, we now have a pretty good idea of how to build our calculator! Here are the basic principles we have discussed so far:

* Represent all numbers using **binary numbering**
* Represent binary digits using electricity: **switched-on for $1$ or -off for $0$**
* Implement math using **networks of transistors**

Now that we have a sketch of how you'd build a calculator, let's turn our focus to programming it.

## Programmability

The first step of figuring out how to program our calculator should be to answer the question, "what does a program even look like, anyways?" We need to make a tradeoff: on one hand, we want it to be relatively easy for humans to construct and understand programs. At the same time, we also want to make it straightforward to execute these programs with electronic circuitry. Those two goals might seem somewhat at odds!

The time-old answer to this dillemma is a programming primitive called an *instruction*.

An instruction has a human meaning: it's a command, like "set the current value to 6 ($0110$)" or "add 4 ($0100$​) to the current value." Each instruction can be represented as a binary number: that's how we represent the instruction in circuitry. As part of designing our computer, we'll define one kind of instruction for each function we built into our calculator; that's how programs will be able to access each function we built into our calculator.

Here's a table of imaginary instructions, where each of the instructions corresponds to one of the functions we used on the quadratic formula in the previous chapter:

> TODO a table of the calculator functions from the previous chapter. Headings: instruction name, definition (copied from the previous chapter) and numerical value

A program, then, can just be an ordered list of instructions. For example, here's our quadratic equation program from the previous chapter, rewritten to use the instructions defined above:

> TODO another table. On the left is each line from the 'program' listing in the previous chapter. In the right column is the binary representation of that instruction

To execute programs like this one, we will need to build a circuit that walks through the program one instruction at a time. For each instruction, this circuit will need to determine which calculator function the instruction designates, and activate the corresponding calculator subcircuit. 

> Animated schematic of an arrow walking through a list of instructions, and activating a corresponding subcircuit for each

So far, all of our instructions have been referring to a 'current value.' What do we mean by that?

In a computer, intermediate values that we are working on are stored in a subcircuit called a *register*. A register is just another network of interconnected transistors, except this network is designed to store binary numbers instead of operating on them. We use registers in our computer whenever we want to remember a binary number so it can be retrieved later. The act of changing the number a register holds is called a *store* or a *write*; the act of retrieving the number from the register is called a *load* or a *read*.

> ### What's in a Name?
>
> You might wonder where the name "register" comes from. The answer is not entirely obvious, and there doesn't appear to be a definitive point in history at which the word came into use. Historically, though, the word "register" meant something like "record:" for example, cash registers are devices that record how much cash the business has received, and many local newspapers are called, "The &lt;Some Place&gt; Register." In a circuit, registers are involved in recording numbers, which might be why the word "register" was chosen for these subcircuits.

Typically, a computer will have a few dozen registers, allowing the computer to track many intermediate values that the program is currently working on. On such a computer, instructions are typically expressed in terms of the registers they operate on; for example, `load A 6` might be human-readable shorthand for an instruction saying "store the binary value of 6 ($110$) in register $A$," and `add A B` might be shorthand for "load the values of registers $A$ and $B$, sum them, and store the result in register $A$."

I'm sure you're getting tired of me saying it, but nonetheless: we will see how to implement a register as a transistor network in the next chapter. Along with everything else :-)

So what did we decide about programs and programmability?

* A program is an ordered **list of instructions**
* Instructions are **commands with a human meaning**
* Instructions have **binary representations** for use in circuitry
* Computers execute programs **one instruction at a time**
* The numbers we're working on are **stored in registers**

Our basic sketch of a simplistic computer is starting to take form. However, we still need one more subcircuit to complete the basic system.

## Memory

So far, we've sketched out a programmable calculator. A computer is a programmable computer. So what we have so far is a computer, right? Technically, yes, it is! But the computer we've described so far is so primitive as to be effectively useless in practice. Let me convince you of why:

Think what it would be like to program a computer like the one we just designed. How much intermediate data does a program typically need to work on? For example, think about our quadratic formula program. As intermediate values, we needed:

* Three inputs: values for $A$, $B$ and $C$
* One thing we're currently calculating
* Five things we already calculated: $-B$, $B^2$, $4AC$, $2A$ and $\sqrt{B^2-4AC}$
* Two outputs (one for the $+$ side of $\pm$ and one for the $-$ side)

That's a total of 11 things we need to store in registers. Do we have 11 registers? On a modern computer, maybe &mdash; on an early computer, probably not! The circuitry for registers requires a lot of space and power relative to other parts of the computer, which makes it infeasible to have a lot of registers. Modern computing architectures usually give you about 16 registers to work with; early computers often had even fewer. What do we do when we run out of registers?

If this sounds contrived, keep in mind the quadratic formula example is a toy, and most programs act on way more data. For example, say you wanted to write a program that takes a year's worth of daily temperature measurements and calculates the average temperature for any date range during that year. Forget the average itself: where would you store those 365+ temperature measurements, if you only have 16 registers to work with?

Fundamentally, there's a relationship between computing and storage. If you have a computer that can do millions of calculations per second, you need it to be able to store millions of numbers to do those calculations on. It doesn't matter if you have a computer that can do a billion calculations per second if there are only ~10 numbers to work on: there's only so much useful work you can do on so few numbers. As such, fast computers require a lot of intermediate data, and vice versa.

That's why all computers &mdash; even the early ones &mdash; included some sort of **random-access memory** (sometimes shortened to **RAM** or just **memory**). Memory provides mass storage for data that isn't needed right now, but may be needed in the near future. In the quadratic formula example from the last chapter, that piece of paper where we were writing down intermediate results served a similar purpose to what memory serves in a modern computer.

Here's the idea: first, we build a small, cheap, low-power circuit that stores a single binary number. We'll see in a future chapter how to do that. Once we have this circuit, we'll make many, many copies of that circuit &mdash; modern computers have billions of copies of this circuit! &mdash; and then we'll arrange them all in a neat row, like this:

> Diagram

We'll assign each number an **address**, which is just a number that uniquely identifies one of the many copies of our number-storage circuit. For example, the first copy of our storage circuit will have address `0`, the second will have address `1`, and so on:

> Diagram

Finally, we'll provide instructions that allow programs to access memory. Fundamentally, we need two new instructions: a `store` instruction, which copies the number from a given register into memory at the given memory address; and a `load` instruction, which copies from a given memory address into a given register. Some computers instead provide a single `move` instruciton which can copy in either direction.

This scheme gives programmers a simple way to 'spill over' when you have more data than you can hold in a register. In the quadratic formula example, we could store the input numbers and all intermediate calculations in memory; in the average temperatures example, we could store the list of daily temperature readings in memory. We will need to copy numbers into registers in order to run calculations on those numbers, but anything we're not calculating right this instant stays in memory.

By happy accident, it also turns out that memory is the solution to a problem we didn't even realize we had yet! We know a program is a list of instructions, but where is the computer storing this list of instructions? Now that we have memory, there's a clear, obvious answer: store the program in memory!

In conclusion,

* Memory is an **array of numbers**
* Each number is identified by a **memory address**
* Memory stores **intermediate values** as well as **programs** themselves

## Computing

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

## Peripherals

Despite all of the amazing work we have done together throughout this chapter, we still managed to build a largely useless computer. Womp womp. What went wrong?

Well, there's no way to get data into the computer. Or out of the computer. Or program it. How is a human, in the real world, supposed to use this thing?

> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.



> Congratulations on completing your whirlwind tour of how computers work. We're not out of the woods yet though. Over the next couple chapters, we'll take a deeper look at how you construct an electrical circuit to implement a von Neumann computing architecture and design programs for it.