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

To model logic using the Boolean values "true" and "false," you use terse "if-then" statements based on conditions that may or may not be true, and draw a conclusion based on them. Try this example:

<center>If (Jill is outside) and (it's raining outside) then (Jill wears a raincoat)</center>

Each group of words in parentheses is a statement that can either be true or false. Both (Jill is outside) and (it's raining outside) are examples of Boolean conditions, which can be thought of as 'input.' (Jill wears a raincoat) is an "output," in that it is true or false purely depending on whether the conditions are true or false. So if Jill goes outside and it's raining outside, then Jill will wear a raincoat; but if it's not raining or Jill isn't outside then Jill does not wear a raincoat (there's no need to, after all).

The "and" in the example is our first **Boolean operator**, a mathematical function that computes a Boolean value based on one more input Boolean values. The common Boolean operators include ...

* AND: produces `true` if both inputs are `true`; else `false`
* OR: produces `true` if either input is `true`; else `false`
* Exclusive-OR, or XOR: produces `true` if the two inputs differ, `false` otherwise
* NOT: produces `true` if the input is `false` and vice versa

Most of these operators have a meaning in terms of logic; try placing them in the example above to try them out. The following table spells out the result of every operator for every possible set of input values:

| a       | b       | not a   | not b   | a and b | a or b  | a xor b |
| ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| `true`  | `true`  | `false` | `false` | `true`  | `true`  | `false` |
| `true`  | `false` | `false` | `true`  | `false` | `true`  | `true`  |
| `false` | `true`  | `true`  | `false` | `false` | `true`  | `true`  |
| `false` | `false` | `true`  | `true`  | `false` | `false` | `false` |

This table starts to look a lot more like math (and thus a lot more like something we could compute) if you replace `true` with $1$ and `false` with $0$:

| a    | b    | not a | not b | a and b | a or b | a xor b |
| ---- | ---- | ----- | ----- | ------- | ------ | ------- |
| $1$  | $1$  | $0$   | $0$   | $1$     | $1$    | $0$     |
| $1$  | $0$  | $0$   | $1$   | $0$     | $1$    | $1$     |
| $0$  | $1$  | $1$   | $0$   | $0$     | $1$    | $1$     |
| $0$  | $0$  | $1$   | $1$   | $0$     | $0$    | $0$     |

Hopefully this makes it clear how Boolean operators mathematical operators over single-digit binary numbers. The question that remains, then, is how to build a circuit that calculates each?

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

In this book, we're only going to cover NOT and AND; if you'd like to figure out how to build the other operators out of transistors, feel free to try it as an exercise.

> One interesting factoid: you don't actually have to puzzle out how to design circuitry for each of the remaining Boolean operators: you can implement any Boolean operator by copying and pasting the circuits we just designed!
>
> The basic idea is to first hook up a NOT subcircuit to the end of an AND subcircuit, such that the output of the AND becomes the input of the NOT; the result is a new type of subcircuit often called "NAND" (because `NAND(a, b) = NOT(AND(a, b))`). There's a well-known proof that you can use NAND gates to implement any Boolean operator, even NOT or AND; for details, see Wikipedia's article on [NAND logic](https://en.wikipedia.org/wiki/NAND_logic).
>
> That said, using NAND logic produces big circuits; if you puzzle out how to directly build each Boolean operator directly out of transistors, you can easily end up with smaller, more space-efficient circuitry.

## Digital Logic Schematics

If you think a little about NAND logic, it may become clear how quickly the complexity of such a circuit can get out of hand: even a single NAND subcircuit is already large enough to start getting confusing, so imagine a subcircuit that combines a handful of them!

To help deal with this complexity without going insane, people have invented an alternate kind of circuit schematic diagram specifically for circuits built out of the 1-bit Boolean operations we oulined above: the **digital logic schematic**. The basic idea behind these is to define a schematic symbol for each kind of Boolean operator; each of these symbols is called a **logic gate**. The main way digital logic schematics reduce complexity is removing the power and grounding lines. Of course, you can't literally remove these and still have a funcitoning circuit; but in digital logic schematics, power and grounding are both taken as implied, and we focus only on showing the relationship between inputs and outputs.

For a full table of schematic symbols for logic gates, see [this Wikipedia article](https://en.wikipedia.org/wiki/Logic_gate#Symbols).

We will adopt logic schematics for the remainder of this page (and, actually, for the rest of the chapter as well). Keep in mind, however, that digital logic schematics are just a different way of writing down the same schematics we've been writing all along &mdash; they're just a way to reduce visual complexity, so we can focus on what really matters.

Make sense? Then let's move on, and see how to build circuits that implement grade-school math on binary numbers ...

## Addition

> Build a one-bit adder with carry out of logic gates
>
> Show how you can string these together to make, as an example, a four-bit adder
>
> Mention other calculations which we'll leave as an exercise to the reader, but recommend they come back to this after reading the chapter where we introduce integers for real

## A Multi-Function Calculator

> We want to revise the harness to add a separate numeric input which chooses the funtion the calculator will carry out. Introduce a harness with multiple calculation modules and introduce the concept of a multiplexer. Maybe sketch how you build a multiplexer, or link out.

## Modularity, Interfaces, Abstraction

(Three ten-dollar words ... I suppose that makes this a thirty-dollar title?)

> Present the ideas of modules, interfaces and abstraction in terms of what we just did
>
> Note once again that this pattern appears all over the place in hardware and software. It's one way (really the only way) we reduce these hyper-complex designs to something a human can fit into their head.

