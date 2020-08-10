---
layout: chapter
title: A Basic Computer&#58; Calculation
---

We finally have the background we need to start building ourselves the digital calculator that underpins all modern computers; let's get cracking!

We're going to draw on the two big ideas we just learned: binary numbering and circuitry. The main insight is that we can use transistors and grounding elements to selectively switch individual lines of a circuit on or off, and use the switching state of each line to represent a single binary bit:

* If a line is switched off (not delivering electricity), we call that $0$
* If a line is switched on (delivering electricity), we call that $1$

Of course, there's already a catch &mdash; this time, the catch is that the circuits we're going to build will get complicated, fast. To deal with this, we're going to use a handful of tried and true techniques that you'll see over and over in hardware and software design: *modular design*, *interfaces* and *abstraction*. These are some pretty big words (hopefully they make us sound super smart!) but all they mean is organizing our design around small, easier-to-understand pieces that can maybe be swapped in and out at will.

More concretely, this means we're going to build a calculator by starting with the basic circuit components we already know about (power, lines, grounding and transistors) and using them to create higher-level building blocks that each do something useful. Then we can build our final calculator circuitry by pasting in copies of our building blocks and hooking them together into a full circuit &mdash; simple!

## A Test Harness

Whether designing software or hardware, when you're building yourself high-level building blocks that cannot stand on their own, it's useful to start out by designing some infrastructure that can be used to test out the building block by itself and make sure we built it correctly. This infrastructure is often called a **test harness**.

Our test harness will be the following circuit:

> A power source with negative leads to a set of switches, which in turn feed into LEDs that pass into a big box labeled [ ? ]. The ? box has output lines leading into a set of LEDs which in turn feed back into the power source. Every element is numbered according to the list below.

Let's take a closer look at what this circuit does:

1. First we have a power source; every circuit needs power!
2. The negative terminal feeds electricity into a set of switches. These switches will work as inputs to the building block we want to test; a human can toggle these switches to change what binary number(s) are fed into the block we're testing
3. Each switch feeds into an LED, which simply shows the user what input value is currently set; if the switch is closed (the input is a $1$), electricity will pass through the LED lighting it up; if the switch is open (the input is $0$) there will be no electricty and the light will stay off
4. Each line then feeds into a box labeled $?$ &mdash; this is the sub-circuit we want to test, and is not part of our harness itself
5. The subcircuit under test ($?$) produces output in the form of one or more lines going 'out' of the subcircuit; each passes through an LED so we can see if the output was $0$ (LED off) or $1$ (LED on).
6. Finally we draw the output lines back to the power source, completing the circuit

This circuit gives us an easy way to test whether any of our subcircuits works &mdash; all we have to do is paste in a copy of our latest design to replace the $?$, using as many input / output lines as we actually need, and provide power to the circuit. Using the switches, we can vary the binary numbers passing into our subcircuit, and use the output LEDs to make sure the right binary numbers came out.

> A one-liner about designing with testing in mind

## 1-Bit Calculation

> Reuse the content we had to introduce boolean logic, as single-bit mathematics.
>
> Introduce the idea of a digital logic gate: a small component of a circuit that implements a boolean operation
>
> Build NOT
>
> Build AND
>
> Build NAND
>
> Invoke NAND logic for the rest

## Digital Logic Schematcs

> Introduce the idea of bulding a circuit purely out of the logic gates we just invented. We know internally that each of these gates is actually a subcircuit built out of power lines, grounding lines and transistors, but we're designing at a "higher level" &mdash; we don't have to think about transistors, we can think in terms of the building blocks we built ourselves. Abstraction!

## Addition

> Build a one-bit adder with carry out of logic gates
>
> Show how you can string these together to make a four-bit adder
>
> Mention other calculations which we'll leave as an exercise to the reader, but recommend they come back to this after reading the chapter where we introduce integers for real

## A Multi-Function Calculator

> We want to revise the harness to add a separate numeric input which chooses the funtion the calculator will carry out. Introduce a harness with multiple calculation modules and introduce the concept of a multiplexer. Maybe sketch how you build a multiplexer, or link out.

## Modularity, Interfaces, Abstraction

(Three ten-dollar words ... I suppose that makes this a thirty-dollar title?)

> Present the ideas of modules, interfaces and abstraction in terms of what we just did
>
> Note once again that this pattern appears all over the place in hardware and software. It's one way (really the only way) we reduce these hyper-complex designs to something a human can fit into their head.







---





































---





We'll design our calculators as a set of 'digital logic gates,' which are just subcomponents of a circuit which receive one or more input lines (representing a binary number), one or more output lines (also representing a binary number), plus a power source and a grounding element:

> Schematic

We're also going to pull on a new concept, one that we're going to see over and over throughout this book: *modular design*. Even if the name sounds fancy (or like biz-speak), all it means is we're going to build a piece of the system that accomplishes some basic task, so we can copy/paste that design into a larger project any time we need.

Each digital logic gate is a "module" that can be incorporated into a larger circuit. 

For example, take a logic gate that adds two 4-bit binary numbers: 

> Schematic



## A Test Harness









This is also the first time in this book we're going to use an idea that appears over and over throughout computers: *modular design*. If that name sounds overly fancy, or like biz-speak, don't worry: all it means is we can swap out the things we build.

Consider this circuit:

> A power source which feeds into a set of classic manual switches, feeding into a [ ? ] component, feeding into a set of LED lights, feeding back to the power source at its positive terminal. Label components using the numbers defined below

We're going to use this circuit as the basis of our calculator. 









## 1-Bit Math









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

## Multi-Function Math

> Introduce the idea that's often useful in logic circuits to be able to 'pick' a line from a list of input lines. Show how you build a multiplexer that picks a circuit given a binary number. Show how you can use a multiplexer to make a multi-function calculator that picks a single function.
>
> Also mention demultiplexing in passing, but feel free not to go into it

## A Calculator

> Build a basic calculator using a bunch of input lines that are manually switched, feeding into each of our subcircuits, and multiplexed to decide which subcircuit is connected to our output line.
>
> Now that we have a calculator, let's make it programmable (next page)