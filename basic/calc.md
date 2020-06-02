---
layout: chapter
title: A Basic Computer&#58; Calculation
---

Now that we understand the basic concepts of building digital logic circuits, it's time to build ourselves a calculator: the kind that lives deep inside the heart of every computer. Once we have our calculator, we can move on to programmability, upgrading our dumb calculator into a rudimentary computer!

## Boolean Logic

The first kinds of calculations we're going to implement using our newfound digital logic circuit skills will be Boolean operations, which are operations on single-bit binary numbers ($0$ and $1$). We'll end up using these to build multi-bit binary operations like addition and subtraction.

The name "Boolean" in Boolean logic comes from George Boole, who is commonly credited with inventing it. The name "logic" comes from a common use of Boolean logic: to model logical reasoning, of the kind 'if `this` then `that`.' To make it easier to understand Boolean logic, we often rename our binary digits to the more human-friendly terms `true` and `false`:

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