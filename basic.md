---
layout: chapter
title: A Basic Sketch
---

In the previous chapter, we learned a little about computers and programs. We decided that a computer is a *programmble calculator*, which means that you give a computer a *program* (which is just a sequence of calculations), and the computer *executes* the program by carrying out each step on its internal calculator.

Now, how does one go about building one of these things? In this chapter we will lay out a basic sketch of the path ahead of us. We'll figure out we need to do, and what problems we'll need to work out along the way. This will give us something of a map to follow over the next few chapters, over which we'll fill in the details.

If a computer is a programmable calculator, then we're going to need a calculator, right? Let's start there!

## Calculation

How are we going to build a calculator out of electronic circuitry?

The key idea we'll use is *switching*. A switch is something you use to turn an electric circuit on or off &mdash; for example, you use switches every day when you turn the lights on and off at your place. More precisely, a switch controls the flow of electricity: when it's on, the switch *completes* a circuit so that electricity can flow through it. When it's off, a switch *interrupts* the circuit, preventing electricity from flowing on through the switch.

How is switching useful for doing calculations on numbers? It's easier to see if you count using *binary* numbering. In binary, there are only two digits, $0$ and $1$, and just like with regular numbers, you use move to the next number place when you run out of digits. The first few binary numbers look like this:

​	$1$ ("one")<br>
​	$10$ ("two")<br>
​	$11$ ("three")<br>
​	$100$ ("four")<br>
​	$101$ ("five")

If it's not immediately clear how binary works, don't worry: we'll take a closer look at binary soon, in the next chapter. For now, the important thing to know is that binary lets us represent numbers &mdash; *any* number, in fact! &mdash; using just the digits $0$ and $1$.

Binary is useful when you're working with switches because there are only two digits &mdash; $0$ and $1$ &mdash; and a switch also only has two possible states &mdash; on and off. That lets us use a switch to represent a binary digit: we can use "switched off" to represent $0$ and "switched on" to represent $1$ in circuitry. To represent a binary number with multiple digits, we use multiple switches; for example, if we wanted to represent a 4-digit binary number, we'd need to use 4 switches &mdash; one for each digit.

For example, let's say we wanted to represent the number 6 in binary. We'd start by counting to six in binary:

​	$1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"),  $101$ ("five"), $110$ ("six")

It looks like we need three digits, so we'll use three switches:

* The 1s place switch, which would be switched off (because the 1s place of $110$ is $0$)
* The 10s place switch, switched on (the 10s place of $110$ is $1$)
* The 100s place switch, swithced on (the 100s place of $110$ is $1$)

In practice, you might want to be able to store much larger numbers; for example, with eight switches, you could store any number from 0 to 255. If we wanted to use those eight switches to store the number six ($110$), all we need to do is set the switches as described above, and then set all the remaining switches off. That is, the 1,000s place switch should be off (set to $0$), as should the 10,000s place, the 100,000s place, and so on. We might write the resulting configuration as $00000110$ to remind us of all those extra switches that we turned off.

Hopefully that gives you a feel for how to represent numbers in binary using circuitry. If things still feel a little fuzzy, that's ok &mdash; we'll go in greater depth over the next chapter of this book.

For our calculator, we need to go a step further: representing numbers is a start, but how do we use circuitry to run calculations on binary numbers represented this way? For example, how would we add two binary numbers using switches?

To make this work, we need to build ourselves a new kind of switch.

A conventional switch is mechanical: in between the *source* terminal (where electricity is coming in) and the *drain* terminal (where electricity goes out), a switch will have some way to *mechanically* connect and disconnect the two terminals: it might be a lever you can flip, a rocker you can push, or something else. To implement our calculator, we're going to want something slightly different: a switch that can be controlled *electronically*.

This ' electronic switch' will instead have three terminals: the source and drain terminals like a conventional switch, plus a new terminal called the *gate.* The gate terminal is how we will operate the switch electronically: when we power the gate terminal, that completes the circuit, allowing electricity coming into the source terminal to flow out the drain terminal. When we power off the gate terminal, that interrupts the circuit, meaning electricity can no longer flow from source to drain:

> Add a basic schematic diagram

Note that the source and drain terminals are always physically connected in this switch! We'll need to rely on some kind of electrochemical effect to control the flow of electricity from source to drain.

What we just described is a circuit element called a *transistor*. In a modern computer, we achieve this using a specific kind of transistor called a "*metal-oxide-semiconductor field-effect transistor*" or "*MOSFET*." In this kind of transistor, the source and drain terminals are physically connected through layers of a silicon-based semiconductor &mdash; our "metal oxide semiconductor." The semiconductor layers are constructed to have a special property: normally, they create an electric field that prevents electricity from passing through, but we can break down that field by applying a charge to the semiconductor layer itself &mdash; via the transistor's "gate" terminal. That's the "field effect" of our MOFSET. The net result? A switch that is 'completes' the circuit when we charge the gate terminal, and 'interrupts' the circuit when the gate is uncharged. An electrically-operated switch!

Transisors turn out to be quite useful for doing math in circuitry. The basic idea is to represent a mathematical operation on binary numbers using a network of interconnected transistors. For example, say you want to build a subcircuit that adds two binary numbers: this subcircuit will have a set of "input" terminals for the digits of the binary numbers we want to add, as well as a set of "output" terminals with the digits of the resulting binary sum. In between those terminals will be a network of transistors, which mix the input signals as needed in order to obtain the correct output signals:

> Another diagram 

We could talk about how this network of transistor might look right now if we wanted: it's not very complicated, although it does take a lot of space to spell it out. For that reason, we'll wait to cover that until the next chapter.

So, in summary, how are we going to build our calculator? Here are the basic principles:

* Represent all numbers and calculations using **binary numbers**
* Represent binary digits using electricity: **switched-on for $1$ or -off for $0$**
* Implement numeric operations using **networks of transistors**

Now that we have a sketch of how you'd build a calculator, let's turn our focus to programmability. 

## Programmability

How do we set up a way to program our new calculator? How do we execute these programs in circuitry? Actually, what should a program even look like anyways?

In answering that last question, we need to make a tradeoff: on one hand, we want it to be relatively easy for humans to construct and understand programs, but at the same time, we also want to make it straightforward to execute these programs using electronic circuitry.

A time-old answer to this dillemma is a programming primitive: the *instruction*. An instruction has a human meaning: it's a command, like "set the current value to 6" or "add 4 to the current value." We will have one instruction for each function we built into our calculator; the instruction is how we make it possible to access that calculator function via a program. Each instruction is *also* a binary number; that's how we represent an instruction in circuitry.

Putting it together, a program will just be an ordered list of instructions. To execute a program, we will need to build a circuit that walks through the program one instruction at a time, each time determining which calculator function the instruction calls for and running the corresponding calculator subcircuit, before continuing on to the next instruction. We, the programmers will to construct programs by lining up instructions so they do something interesting. The computer will execute programs using transistors.

Here's a table of imaginary instructions, where each of the instructions corresponds to one of the functions we used on the quadratic formula in the previous chapter:

> TODO a table of the calculator functions from the previous chapter. Headings: instruction name, definition (copied from the previous chapter) and numerical value

And, for completeness, here's what solving the quadratic equation would look like using our imaginary instruction set:

> TODO another table. On the left is each line from the 'program' listing in the previous chapter. In the right column is the binary representation of that instruction

So far, all of our instructions have been referring to a 'current value.' What does this mean?

In a computer, intermediate values that we are working on are stored in a subcircuit called a *register*. A register is just another network of interconnected transistors, except this network is designed to store a binary number instead of operate on one. We use registers in our computer whenever we want to remember a binary number so it can be retrieved later. The act of changing the number a register holds is called a *store* or a *write*; the act of retrieving the number from the register is called a *load* or a *write*.

Typically, a computer will have a few dozen registers, allowing the computer to track many intermediate values that the program is currently working on. On such a computer, instructions are typically expressed in terms of the registers they operate on; for example, `load A 6` might be human-readable shorthand for an instruction saying "store the binary value of 6 ($110$) in register $A$," and `add A B` might be shorthand for "load the values of registers $A$ and $B$, sum them, and store the result in register $A$."

I'm sure you're getting tired of me saying it, but: we will see how to implement a register as a transistor network in the next chapter. Along with everything else :-)

So what did we decide about programs and programmability?

* A **program** is an ordered list of **instructions**
* An instruction has a human meaning, as a **command**
* An instruction has a **binary representation** for circuitry
* Computers execute programs **one instruction at a time**
* Instructions store and use intermediate values in **registers**

Our basic sketch of a simplistic computer is starting to take form. Let's turn our focus to a different but equally important problem a computer must solve: mass data storage.

## Memory

So far, we've sketched out a computer that executes programs made of instructions, executing each instruction one by one by running the corresponding calculation subcircuit. All intermediate values used by these instructions are stored in registers, and each instruction stores its result in a register. With care, we can construct a sequence of instruction that calculates something interesting, and stores it in a register. What we have is already a recognizable computer!

But the computer, as we've designed it, is not very useful yet. What if we need more intermediate state than we can store in our registers? Say, for example, we wanted to calculate the average temperature over the past year by summing the high and low temperature of each day; where would we store those ($365 \times 2 =$) $730$ temperatures, if for cost reasons a computer only has a few dozen registers?

Also, we've made a glaring omission: a program is a list of instructions that the computer executes; but where is that program stored? How does the computer know what instructions were given to it by the programmer?

We usually solve both these problems with another component we haven't talked about yet: random-access memory, or "RAM." As is the norm, this book will usually call RAM "memory" for the sake of brevity.

The basic idea 

> Idea: an array of 8-bit integers. Warning: we haven't defined "bit" yet. An 8-bit integer is called a byte. Usually, memory is pretty big: if your computer has 4 GB of RAM, that means your computer's memory has 4 billion slots, each of which can store an 8-bit integer.
>
> An address identifies each byte in memory. The first 8-bit integer is at address 0, the second is at address 1, and so on. 
>
> To make memory accessible to programs, we provide instructions that store into and load from memory. A store instruction copies the number of a designated register into a given memory address, and a load instruction copies the value stored at a given memory address into the designated register. Work examples.
>
> This provides a simple way to 'spill over' when you have more data than you can hold in registers.
>
> If you need a number with more than 8 bits, you can just commandeer multiple neighboring 8-bit integers. For example, to store a 16-bit integer at address 0, you might store the first eight digits in address 0 and the last eight digits in address 1.
>
> What about the program itself? With memory, we now have a simple place to store the program: as a sequence of instruction stored in memory
>
> Problem: bootstrapping. Firmware puts something in RAM to execute on power on. Whatever code it loaded picks it up from there. Usually that code loads more code, or provides a programmer some way to enter code.

## Computing

> All up review. This is the von Neumann architecture and all conventional hardware uses it today
>
> Also introduce the term ISA

## Peripherals

> This computer is still not very useful. No way to get data in or out
>
> Peripherals. Common device classes
>
> How do we make this work? Outline some strategies. We’ll come back later.



> Congratulations on completing your whirlwind tour of how computers work. We're not out of the woods yet though. Over the next couple chapters, we'll take a deeper look at how you construct an electrical circuit to implement a von Neumann computing architecture and design programs for it.