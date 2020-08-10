---
layout: chapter
title: A Basic Computer&#58; Calculation
---

We finally have the background we need to start building ourselves the digital calculator that underpins all modern computers; let's get cracking!

We're going to draw on the two big ideas we just learned: binary numbering and circuitry. The main insight is that we can use transistors and grounding elements to selectively switch individual lines of a circuit on or off, and use the switching state of each line to represent a single binary bit:

* If a line is switched off (not delivering electricity), we call that $0$
* If a line is switched on (delivering electricity), we call that $1$

Of course, there's always a catch &mdash; this time, the catch is that the circuits we're going to build will get complicated, fast. To deal with this, we're going to use a handful of tried and true techniques that you'll see over and over in hardware and software design: *modular design*, *interfaces* and *abstraction*. These are some pretty big words (hopefully they make us sound super smart!) but all they mean is organizing our design around small, easier-to-understand pieces that can maybe be swapped in and out at will.

More concretely, this means we're going to build a calculator by starting with the basic circuit components we already know about (power, lines, grounding and transistors) and using them to create higher-level building blocks that each do something useful. Then we can build our final calculator circuitry by pasting in copies of our building blocks and hooking them together into a full circuit &mdash; simple!

## A Test Harness

Whether designing software or hardware, when you're building yourself high-level building blocks that cannot stand on their own, it's useful to start out by designing some infrastructure that can be used to test out the building block by itself and make sure we built it correctly. This infrastructure is often called a **test harness**.

Our test harness will be the following circuit:

> A power source with negative leads to a set of switches, which in turn feed into LEDs that pass into a big box labeled [ ? ]. The ? box has output lines leading into a set of LEDs which in turn feed back into the power source. Every element is numbered according to the list below.

Let's take a closer look at what this circuit does:

1. First, we have a power source. Every circuit needs power!

2. The negative terminal feeds electricity into a set of switches. These switches will work as inputs to the building block we want to test; a human can toggle these switches to change what binary number(s) are fed into the block we're testing.

3. Each switch feeds into an LED, which simply shows the user what input value is currently set; if the switch is closed (the input is a $1$), electricity will pass through the LED lighting it up; if the switch is open (the input is $0$) there will be no electricty and the light will stay off.

4. Each line then feeds into a box labeled $?$ &mdash; this is the sub-circuit we want to test, and is not part of our harness itself.

5. The subcircuit under test ($?$) produces output in the form of one or more lines going 'out' of the subcircuit; each passes through an LED so we can see if the output was $0$ (LED off) or $1$ (LED on).

6. Finally, we draw the output lines back to the power source, completing the circuit

This circuit gives us an easy way to test whether any of our subcircuits works &mdash; all we have to do is paste in a copy of our latest design to replace the $?$, using as many input / output lines as we actually need, and provide power to the circuit. Using the switches, we can vary the binary numbers passing into our subcircuit, and use the output LEDs to make sure the right binary numbers came out.

When designing hardware or software, designing a test setup like this is often a good idea for how to start your project.

## 1-Bit Calculation

With a working test harness, it's time to start building the basic elements of our calculator. We're going to start with **Boolean** math: the math of single-bit calculations.

Boolean math is named after George Boole, who published the basis of Boolean math back in the 1800s. Boolean math is also known as Boolean logic, as it was originally designed to model logical reasoning (of the form, "if `this` then `that`"). Boolean logic assigns a human-friendly name to the binary digit values $0$ and $1$:

| Binary Value | Boolean Value |
| ------------ | ------------- |
| $0$          | `false`       |
| $1$          | `true`        |

To model logic using the Boolean values "true" and "false," you use terse "if-then" statements based on conditions that may or may not be true, and draw a conclusion based on them. For example, take this (rather benign) statement:

<center>If (Primer is a book) and (Jill is reading Primer) then (Jill is reading a book)</center>

Each group of words in parenthesis is a statement that can either be true or false. Both (Primer is a book) and (Jill is reading Primer) are conditions that can be thought of as "inputs" to this statement; (Jill is reading a book) is an "output," in that whether it is true or false depends purely on whether the conditions are true and false. So if Primer is a book and Jill is reading Primer, then Jill is reading a book; but if JIll is not reading Primer then doesn't follow that Jill is reading a book.

> Oops we'd do better with an if-and-only-if example

The "and" in the example above is our first example of a **Boolean operator**, which computes a Boolean value based on one more input Boolean values. The common Boolean operators include ...

* AND: produces `true` if both inputs are `true`; else `false`
* OR: produces `true` if either input is `true`; else `false`
* Exclusive-OR, or XOR: produces `true` if the two inputs differ, `false` otherwise
* NOT: produces `true` if the input is `false` and vice versa

Most of these functions are fairly intuitive; try placing them inside if-then statements like the example above and see how they work out. The following table also spells out the result of each operator for every possible combination of input values:

| a       | b       | not a   | not b   | a and b | a or b  | a xor b |
| ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| `true`  | `true`  | `false` | `false` | `true`  | `true`  | `false` |
| `true`  | `false` | `false` | `true`  | `false` | `true`  | `true`  |
| `false` | `true`  | `true`  | `false` | `false` | `true`  | `true`  |
| `false` | `false` | `true`  | `true`  | `false` | `false` | `false` |

So, how would one build a circuit to implement each of the Boolean operators?

Let's start with NOT, because it has only one input and one output, making it easier to work with. Here's a schematic for a small subcircuit that implements NOT:

> Power leads to a junction. One end of the junction goes straight to output; the other goes through a transistor to ground. The transistor is controlled by the input line

The basic idea is to use the input line to gate a transistor that leds from the power line to ground. When the input line is $1$, the transistor completes the path between power and ground, causing all power to be drained out of the circuit, leading none to travel to the output line:

> Same diagram, but bold the input line and the lines along which power flows to ground

When the input line is $0$, the transistor doesn't complete the path between power and ground, so power flows straight to the output line:

> Same diagram, but the input line is not bolded; bold the lines along which power flows out

And there's our NOT subcircuit! Just for completeness, let's show what our test harness looks like with our NOT circuit swapped in for $?$:

> Show two copies of the full test harness schematic, one where we close the input switch and send all power to ground, another where we leave the input switch open and send power out

Feeling comfortable with NOT? Let's ramp up the difficulty a little bit; how about an AND subcircuit?

Now we need to accept two input lines and produce a single output line. Here's a simple subcircuit which does what we want:

> Input A feeds through a transistor (controlled by B) to an output line

The basic idea for this subcircuit is simple: transistors already implement AND for us!

Think about what happens when there's no power being delivered to the input line: then it doesn't matter whether or not the control line has opened or closed the transistor, because there's nothing to 'pass through' the 'gate' whether or not it's 'open.'

> Diagram showing the case where input is 0, control is 1

Similarly, if there's no electricity along the transistor's input line, then the transistor acts like an open switch: no electricity can pass from the input line to the output line:

> Diagram showing the case where input is 1, control is 0

Only if both are delivering electricity will the transistor deliver electricity along the output line: just as required by the AND operator!

> Diagram showing input 1, control 1

In this book, we're only going to cover NOT and AND; if you'd like to figure out how to build the other operators out of transistors, feel free to try it as an exercise. One interesting factoid: you actually don't have to puzzle out how to design circuitry to implement the other Boolean operators if you don't want to; it's actually possible to use copies of NOT and AND to implement any Boolean operator. This famous proof is sometimes referred to as [NAND logic](https://en.wikipedia.org/wiki/NAND_logic); feel free to click the link to learn more.

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

