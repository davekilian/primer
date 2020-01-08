---
layout: chapter
title: A Basic Computer&#58; Digital Logic
---

Now that we have a basic grasp of circuits, transistors and grounding, let's build our first digital calculator.

> Old content, maybe rework into here:
>
> The basic idea behind digital circuits is to represent numbers on the circuit as voltages across wires in a circuit. We typically use binary, and we typically choose some voltage threshold $v$, such that when the voltage across a wire is above $v$, we consider that wire to be a 1; otherwise, when the voltage is below $v$, we consider that wire to be a 0. We then use circuit elements to perform mathemtical operations on our binary numbers, giving us a rudimentary form of electronic calculator.

## Logic Gates

> Explain at a high level what a logic gate is - a subcircuit that we can insert into a larger circuit to perform some kind of digital operation.
>
> Each logic gate receives one or more lines of input and produces one or more lines of output. When the logic gate is added to the circuit, we only have to worry about the input and output lines, and as long as everything is hooked up correctly, we can ignore the circuitry inside the logic gate and what happens internally.
>
> When we design logic gates, we don't worry about voltage: we assume a voltage of 0 maps to a binary 0 and a nonzero voltage maps to a binary 1. Well, but actually thresholds, like we mentioned back in the binary chapter.

## Boolean Logic

> Explain that boolean logic is the mathematics of single-digit binary operations. 
>
> Often we label the digit 0 as 'false' and 1 as 'true,' because this maps boolean values to how logic works in our spoken language.
>
> Introduce not, and, or, xor and show them all in a truth table
>
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
> Once you have a NAND gate, you can implement all other boolean logic gates out of one or more NAND gates wired together. Link to Wikipedia, which I remember having an article about this.
>
> We're now done working with analog circuits - from this point forward, all circuits will be designed in terms of boolean logic gates rather than 

## Integer Math

> Build an adder
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