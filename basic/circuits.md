---
layout: chapter
title: A Basic Computer&#58; Circuits
---

Modern computers are [digital circuits](https://en.wikipedia.org/wiki/Digital_electronics), which are [electric circuits](https://simple.wikipedia.org/wiki/Electrical_circuit) that are designed to operate on discrete values (in a vast majority of cases, just two: 0 and 1, binary).

## Electric Circuits

The fundamental components in an electric circuit are a power source and a wire:

> Diagram of the most basic possible circuit connecting one terminal of a power source to another

As we can see in the diagram above, circuits are caled circuits because they form a loop, starting at one end of the power source and ending at the other.

What happens when we connect this circuit? The simple answer is that electrons flow from the **negative terminal** of the power source (labeled $-$ in the diagram above) to the **positive terminal** (labeled $+$)

> If it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it is: the first people to study electricity and circuits guessed wrong about what direction electrons were flowing, but everyone was already using this notation by the time we figured out we had it backwards, so it ended up being too late to change it!

It's worth taking a quick look at the physics behind electrical circuits, so we can define basic terms like *charge*, *current* and *voltage*:

If you've ever popped a balloon or vented a pressure cooker, you've experienced the tendency of air to equalize in pressure: if you give high-pressure air a way to move to lower pressure it will &mdash; sometimes explosively! High pressure air is just air where the atoms are tightly packed, so another way of describing this phenomenon is that tightly-packed air will spread out if you give it room to.

Electrons, the particles that make up electricity, do something similar: if you have a bunch of tightly-packed electrons and give them room to spread out, they will. Circuits use this to move electrons through the wire in a consistent direction.

To make this work, we set up a power source where one end (the negative terminal) is densely packed with electrons; the other end (the positive terminal) is more loosely packed. Then we connect both terminals with a wire, giving the densely packed electrons room to expand (into the positive terminal), so they do, flowing along the wire in the process:

> Same diagram, but now we label the terminals in terms of their potential and use arrows to show the flow of electrons

Much of the study of electrical engineering and circuit design is to find interesting things you can do with this predictable flow of electrons. There are quite a few interesting things it turns out you can do; notably, build computers!

## Terms for Circuits

Physicists and engineers who study electronics have terms to describe the flow of electrons:

Any time you count electrons, that quantity is called **charge**. Charge is measured in **Coulombs**, which are abbreviated $C$. We won't end up talking much about charge or Coulombs at the level of detail we're going to look at circuits.

**Current** refers to the movement of electrons; if you want to measure the rate at which electrons are moving, you're measuring **amperage**. The name derives from the corresponding unit of measurement: **amperes**, often shortened to **amp** or abbreviated $A$. In the context of electrical circuits, amperage is typically used to describe the number of electrons which through the circuit (from the negative terminal to the positive terminal) every second.

Any time you talk about a difference in charges, that quantity is often called **voltage**; like with amperage, the name 'voltage' derives from the corresponding unit of measurement: **volts** ($V$). Volts measure differences in **electrical potential**, which is analogous to measuring differences in air pressure in our example earlier.

In general, increasing the voltage of a circuit's power source causes the amperage to rise, because the additional 'pressure' pushes more electrons through the wire faster. However, the amperage also depends on the absolute level of charge at each terminal of the power source: adding more charge while keeping the voltage the same also increases amperage.

## Digital Circuits and the Transistor

Now that we understand electrical circuits in general, let's take a closer look at digital circuits.

The basic idea behind digital circuits is to represent numbers on the circuit as voltages across wires in a circuit. We typically use binary, and we typically choose some voltage threshold $v$, such that when the voltage across a wire is above $v$, we consider that wire to be a 1; otherwise, when the voltage is below $v$, we consider that wire to be a 0. We then use circuit elements to perform mathemtical operations on our binary numbers, giving us a rudimentary form of electronic calculator.

To do math on our electrical circuits, we need to add another component in addition to the power source and the wire: a **transistor**.

> Mention the transistor is the basic building block of modern computers, which is why Moore's Law (link to Wikipedia again) measures computer hardware progress in transistors.
>
> To understand transistors, first have to understand a more classic circuit element: a **switch**, which can be **open** (breaking the circuit, such that there is no path from the negative terminal to the positive terminal anymore) or **closed** (completing the circuit, allowing electrons to flow).
>
> In digital circuitry, transistors act as electrically-driven swiches. Diagram with an emitter, collector and base. When voltage is applied to the base, it allows electricity to flow from the emitter to the collector, as if closing a switch; when no voltage is applied to the base, there is no longer flow, acting as if the switch were opened.

## Logic Gates

> Define boolean logic inline and show a table laying out the and, or and xor operations.
>
> Start with the not gate. I guess to do this we first need to go back and define ground. But once you do, a not gate uses a transistor connected to a ground to 'drain' current away from the output line. So when the transistor is on, current is allowed to flow to ground, resulting in infinite potential and draining current away from the output line.
>
> There's a good diagram on this page: https://www.instructables.com/id/Logic-Gates-with-NPN-transistors/
>
> Then and, which is an input line which passes through two inline transistors to reach an output line - both transistors must be on for current to pass from the input line to the output line. Again, a good diagram for reference: https://www.instructables.com/id/Logic-Gates-with-NPN-transistors/
>
> Now you actually have enough to build everything else: https://en.wikipedia.org/wiki/NAND_logic
>
> With our newfound gates we can now zoom out to the logic level, looking at circuits as a sequence of logic gates and no longer worrying about lines, grounds, power sources and so on. In fact, you could even build a logic circuit out of something other than electrical charges and impulses. Link to a water computer or something.

## A Digital Calculator

> Back to logical circuits, start by building a few mathematical tools, like an adder, multiplier, shifter
>
> Build flipflops and maybe SRAM(?) for storing the numbers you want to input, and the numbers you want to output
>
> Now we can build a calculator - almost. We currently have a separate calculator for each type of thing, which is kind of useless. Build multiplexers and demultiplexers for aggregating and selecting values. Now you can build a real calculator.

## Our Proto-Computer

> What we have on our hands is a sort of proto-computer. It's a calculator, but it's sure not programmable. Let's figure out how to add programmability next.