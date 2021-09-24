---
layout: chapter
title: A Basic Sketch&#58; Calculation
---

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
