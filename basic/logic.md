---
layout: chapter
title: A Basic Computer&#58; Digital Logic
---

In the previous chapter, we introduced the basic components that underly digital circuitry: circuits, transistors and grounding. Now we're going to switch to talking about *digital* circuits.

Digital circuits deal with descrete values; typically, we choose exactly two discrete values: the binary digits $0$ and $1$. A digital circuit is ultimately just a circuit; that a circuit is 'digital' has to do with how the designer builds the circuit and intends it to be used.

The basic idea behind digital circuits is to represent numbers as binary using voltages and current: we treat any line with current passing through it (that is, any line with a nonzero voltage) as a binary $1$; then, to us, any line with no current passing through it (zero voltage) is a binary $0$. We then use combinations of circuitry, transistors and grounding to perform mathematical operations on these binary numbers, by manipulating voltages and current appropriately.

Let's start with the simplest kind of digital operations: Boolean logic.

## Boolean Logic

The name "Boolean" comes from the name `TODO` Boole, who is commonly credited with inventing it.

> I forgot the guy's first name (maybe William??), and there's no wi-fi on the plane so I can't look it up right now ... womp womp

Boolean logic is the mathematics of single-digit binary operations. We commonly use Boolean logic to model logical reasoning, of the kind 'if `this` then `that`.' To make it easier to understand Boolean logic, we often rename our binary digits to the more human-friendly terms `true` and `false`:

| Binary Value | Boolean Value |
| ------------ | ------------- |
| $0$          | `false`       |
| $1$          | `true`        |

To model logic using Boolean math, we use terse statements that could either be `true` or `false`, and then operate on them. For example

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