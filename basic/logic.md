---
layout: chapter
title: A Basic Computer&#58; Digital Logic
---

---

TODO: rename this page, it should be obvious in the TOC that we're going to build our calculator now

---

Now that we understand how to build classical analog (non-digital circuits), and we understand binary, it's time to get cracking on our computer! We're going to start by designing a digital circuit that can perform calculations.

A digital circuit is no different from a regular circuit; the only thing that makes a circuit "digital" is our design goal. Analog (non-digital) circuit design usually involves carefully designing the circuit to make sure electricity flows through all parts of the circuit at a predictable rate; digital circuits focus more on switching whole parts of the circuit on and off.

In particular, we're going to build digital logic circuits. That basically means that we're going to use switching to represent binary numbers: a switched-on portion of the circuit where electricity can flow corresponds to a binary 1, whereas a switched-off part of the circuit where electrons cannot flow corresponds to a binary 0:

> Diagrams showing a switched-on line labeled 1 and a switched-off line labeled 0

In this chapter, we're going to use the transisitor and grounding elements from the previous chapter to build circuits that perform calculations on binary numbers. But before we build up to full arithmetic, we need a more basic kind of digital operation: Boolean logic.

## Boolean Logic

The name "Boolean" in Boolean logic comes from George Boole, who is commonly credited with inventing it. Boolean logic is the mathematics of single-digit binary operations.

One common use of Boolean logic is to model logical reasoning, of the kind 'if `this` then `that`.' To make it easier to understand Boolean logic, we often rename our binary digits to the more human-friendly terms `true` and `false`:

| Binary Value | Boolean Value |
| ------------ | ------------- |
| $0$          | `false`       |
| $1$          | `true`        |

To model logic using Boolean math, we use terse statements that could either be `true` or `false`, and then operate on them. For example,

> TODO come up with an example

Now we can define **Boolean operations**, which take one or more Boolean values as input and produce a Boolean value as output. That might sound like a mouthful, but Boolean operations are pretty straightforward in practice.

The most basic Boolean operation is `not`, which simply inverts its input value. So `not true` is `false` and `not false` is `true` &mdash; simple!

There are also Boolean operations that take two inputs and produce an output. For example, the `and` operation, which takes two Boolean values and outputs `true` if both inputs were `true`, or `false` otherwise. There's also an analogous `or` operation which is `true` if either input is `true`, as well as an `xor` (short for "exclusive-or") which returns `true` if the inputs don't match. The following table summarizes these operations:

| a             | b             | a and b       | a or b        | a xor b       |
| ------------- | ------------- | ------------- | ------------- | ------------- |
| `true` $(1)$  | `true` $(1)$  | `true` $(1)$  | `true` $(1)$  | `false` $(0)$ |
| `true` $(1)$  | `false` $(0)$ | `false` $(0)$ | `true` $(1)$  | `true` $(1)$  |
| `false` $(0)$ | `true` $(1)$  | `false` $(0)$ | `true` $(1)$  | `true` $(1)$  |
| `false` $(0)$ | `false` $(0)$ | `false` $(0)$ | `false` $(0)$ | `false` $(0)$ |

Make sense? Then let's try building a couple of these operations using the circuit elements we covered in the previous chapter.

We're going to start by implementing `not`. 

> Build a not gate using a power line, an input line, an output line and a grounded line. The power line feeds into a junction which splits into the output line and a grounded line. A transistor on the output line acts as a gate between the junction and the ground. The input line is connected to the transistor's switching line.
>
> The result of this is as follows: when the input is 0, the transistor is open, so no current can flow from the power line to the ground. Instead, all current passes to the output line. Thus when the input is 0 (no current), the output is 1 (current).
>
> When the input is 1 (current), the transistor is closed, so the junction is exposed to ground. The ground has roughly infinite voltage compared to the output line, so approximately all power drains to ground, and approximately no power is left for the otput line. Thus when the input is 1 (current), the output is 0 (no current).
>
> Now we build an and gate. 
>
> Finally we connect the output of an and gate to the input of a not gate, obtaining a newer gate called a nand gate. 
>
> Once you have a NAND gate, you can implement all other boolean logic gates out of one or more NAND gates wired together. Link to Wikipedia, which I remember having an article about this

## Logic Gates

> We're now done working with analog circuits - from this point forward, all circuits will be designed in terms of *logic gates*
>
> Explain at a high level what a logic gate is - a subcircuit that we can insert into a larger circuit to perform some kind of digital operation. A logic gate works a lot like a circuit component, but instead of being a fundamental component, it's built out of one or more fundamental components. Maybe mention that this is our very first abstraction, and define abstraction as well.
>
> Each logic gate receives one or more lines of input and produces one or more lines of output. When the logic gate is added to the circuit, we only have to worry about the input and output lines, and as long as everything is hooked up correctly, we can ignore the circuitry inside the logic gate and what happens internally.

## Integer Math

> Build an adder out of boolean logic gates
>
> Then describe a few other arithemtic circuits you might want to build, and find a nice resource to link to for information about how to do that, if the reader is interested.

## Multiplexing

> Introduce the idea that's often useful in logic circuits to be able to 'pick' a line from a list of input lines. Show how you build a multiplexer that picks a circuit given a binary number.
>
> Also mention demultiplexing in passing, but feel free not to go into it

## A Calculator

> Build a basic calculator using a bunch of input lines that are manually switched, feeding into each of our subcircuits, and multiplexed to decide which subcircuit is connected to our output line.
>
> Now that we have a calculator, let's make it programmable (next page)