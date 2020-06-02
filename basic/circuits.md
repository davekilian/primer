---
layout: chapter
title: A Basic Computer&#58; Circuits
---

Modern computers are built out of electronic circuits, so to understand what goes on physically inside a computer, we're going to need to learn a thing or two about circuits. That's just what we'll do here!

## Circuit Basics

The goal of an electronic circuit is to set up a flow of electricity, usually through something (or a lot of somethings) that use the electricity to do something interesting: you might hook up an LED to the circuit to make a light turn on or off, or to get a speaker to make sound, and so on. These "somethings" that you're trying to deliver electricity to are often called **components** of the circuit.

To understand circuits, we use a kind of diagram called a **schematic**. Schematic diagrams give us a broad outline of how the circuit is constructued without needing to delve into nitty-gritty details. Let's take a look at the basic building blocks of circuits and how to visualize them using schematic diagrams.

The first component we'll want to look at is the **line**, which is also sometimes called a **wire**:

> TODO just a line with a couple of terminals visualized using little circles at each end

A line is just a conduit for electricity to pass through. They don't do anything interesting; they're just the way we hook things up to other things. At each end of a line is a **terminal** (the black circles in the diagram). A terminal is a connection point. Each circuit component provides a small number of terminals which are used to connect things together.

Since lines allow electricity to flow, but don't cause electricity to flow, we need another component in our circuit to make electrons move. Enter the **power source**:

> TODO schematic of a DC power source

A power source is anything that induces the flow of electricity. In the real world, a power source might be a battery, or a generator; there are separate schematic symbols for each:

> TODO schematic of a battery, or a generator

Each power source is shown with two terminals, labelled $-$ ("negative") and $+$ ("positive"). When you connect these two terminals together, electricity flows from the negative terminal to the positive terminal:

> TODO schematic showing the most basic circuit: a power source connected to itself by a single line

Congratulations us: we just built the minimum viable circuit! This circuit allows electricity to flow from the power source's negative terminal to its positive terminal, but otherwise doesn't do anything with that flow of electricity; all that's left to do now is add some components that actually do stuff in between the power source's terminals. 

The diagram above also gives us a hint why circuits are called "circuits:" they always end up forming a loop, where electricity starts at one point in the loop and flows all the way around until it ends up back at the beginning.

## The Physics of Circuitry

Now we understand the basics of constructing a circuit; but what's going on when we connect the terminals of a power source together? Why does electricity flow?

At the atomic level, electricity is just the flow of electrons (a subatomic particle) through a material. Circuits rely a fundamental property of electricity: that electrons repel each other. To take advantage of this, we set up a power source with very tightly-packed electrons at the $(-)$ terminal and loosely-packed electrons at the $(+)$ terminal. We separate the two terminals by an **insulator**, which is just a name for any material that doesn't allow electrons to pass through it (at least not very easily).

Let's say our power source is a conventional battery, and let's zoom into the battery to see what's going on inside:

> Diagram showing the inside of a battery: two cells, one tightly packed with electrons and one loosely packed, with insulators providing a barrier providing nowhere to go

As we see in this diagram, the battery internally consists of two globs of material, called **cells**. The negative cell (the one connected to the negative terminal of the battery) consists of densely packed electrons; the positive cell (connected to the positive terminal) has electrons too, but they're less densely packed. The electrons in each cell continually try to repel each other, but the cells are surounded by insulation, so the electrons have nowhere to go. Everything is stable at this point.

Now say we connect the two terminals using a **conductor** (which is just a name for any material that *does* allow electrons to pass through easily):

> Diagram showing a sort of pipe surrounded by insulation connecting the two cells of the battery

All of a sudden there's somewhere for the electrons to go! Inside each cell, the electrons are still repelling from one another, in all directions, but now there's a small break in the insulation layer, allowing the electrons to repel each other into the conductor &mdash; which is our circuit line. The electrons can repel each other through the circuit line, but must stay inside it because the line is also surrounded by insulation.

> Same diagram showing electrons repelling each other into the pipe

So now we have electricity travelling in two directions: out of the negative terminal, down the circuit line toward the positive terminal; and out of the positive terminal, moving down the circuit line in the opposite direction. Give this some time to play out (not very much  &mdash; these electrons are moving at a trillion miles per hour) and the two streams of electrons will eventually collide:

> Same diagram showing the line filled with electrons on both ends

Now begins a tug-of-war. Who will win? Remember the electrons coming from the negative terminal are much more tightly packed, and are thus repelling each other much harder than the electrons coming out of the positive terminal. So the negative-terminal electrons win the tug-of-war and continue pushing down the line until reaching the positive cell of the battery:

> Same diagram showing the negative-terminal electrons completing the circuit from negative to positve cell

This is a new steady state for the system: as long as the electron density in the negative cell is sufficiently higher than in the positive cell, those electrons repel each other more strongly and continually win the tug of war, causing electricity to continue flowing in the same direction. We've reached a steady state: electricity flowing from the negative cell of the battery to the positive one:

> Final zoomed-in battery diagram with arrows showing the flow of electricity
>
> Another diagram where we zoom out to show the schematic again, with the same arrows

> By the way, if it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it sort of is.
>
> The first people to study electricity and construct circuits knew electricity was moving through their circuits, but since circuits are loops, they couldn't be sure which direction the electricity was moving. So they guessed, having a 50/50 chance of being right; as fate would have it, they guessed wrong. By the time we realized we had it backwards, people all over were already using this notation, making it too late to switch to a more intuitive system.
>
> And lo, to this day, electrons are thought to be 'negatively' charged and flow from the negative terminal to positive &mdash; oops!

Something interesting happens if you wait a long time for this to continue: eventually, you'll find that enough electrons have been pushed from the negative cell to the positive cell that the density of electrons in each cell has more or less equalized. At this point, both cells repel electrons down the line equally forcefully, and so neither wins the tug-of-war and the electrons stop moving:

> Diagram showing both cells with equal electron densities and arrows in the circuit line pointing at each other to denote equal pressure

You and I would call this situation a 'having a dead battery.' To get electrons moving again, we would need to recharge this battery, which means externally doing work to pull electrons out of the positive cell and push them into the negative cell. This puts the cell out of balance in the way we need to move electricity through the circuit!

That's the physics of circuitry in a nutshell. In practice, a lot of the work of designing circuits revolves around precisely controlling the flow of electrons through the circuit, making sure each component is delivered a steady flow of the right amount of electricity. This requires understanding the relationships between fundamental quantities like

* **Charge** (measured in *Coulombs*, $C$): a total number of electrons, e.g. in a cell of the battery
* **Current** (measured in *Amperes*, $A$): a rate at which electrons flow, e.g. through a circuit line
* **Voltage** (measured in *Voltage*, $V$): the degree to which one side of an electronic tug-of-war wins over the other (e.g. between the two cells of a battery)
* **Resistance** (measured in *Ohms*, $\Omega$): how easily electrons can flow through a material, or more precisely how much voltage is needed to produce a given amount of current

We won't cover these quantities in this book because we don't need to, but you're encouraged to learn on your own if you're interested. If you plan to build your own circuits, you'll certainly need to understand what these quantities mean and how they're related in circuitry.

## Grounding

Now we understand the basic elements of a circuit and how electricity moves through a circuit. To build a calculator, we still need a few more circuit components. The next component we'll examine is the **ground**:

> Schematic icon for a ground

A ground is called a ground because you usually ground a circuit by literally connecting the circuit to the ground; the Earth is the largest and best grounding component around!

As a circuit component, grounds exist to soak up electricity. You can almost think of a ground as a way of pulling electrons out of a circuit: if a ground is connected to a circuit, all incoming electricity from the negative terminal of the battery is 'drained' into the ground, leaving none to flow on into the rest of the circuit:

> Diagram showing electricity flowing to a ground instead of to the positive terminal of a battery

What makes grounding useful in designing our computer is that we can use grounding to effectively 'shut off' part of the circuit (the part of the circuit that's 'downstream' of the ground). For example, say we added some electrical component (denoted by $?$) to our circuit like this:

> The same circuit schematic showing a new $?$ component downstream of the ground junction

In this circuit, the $?$ element doesn't receive any electricity, even though it's connected to the junction, because all electricity leaving the negative terminal of the battery travels through the junction to the ground.

From a physics perspective, grounding works kind of like adding a third battery cell to your circuit. This cell has even less-densely packed electrons than either cell of the actual battery, so inside a junction that connects the battery's positve terminal, negative terminal and ground together, you get a three-way tug of war that the ground loses; so all electricity flows to the ground (from *both* battery terminals):

> Diagram showing the tug-of-war and electrons flowing from both battery terminals into the ground

The ground also has enormous capacity, such that no matter how long you send power to the ground, the ground's electron density doesn't change to any degree we can measure. This means that a ground cannot be depleted and never needs to be 'recharged' like a battery.

## Switching

In the kinds of circuits we're going to be looking at, grounding is most useful when combined with another element called a **switch**.

A switch is just a way of connecting and disconnecting a line in a circuit. We use the following symbol in schematic diagrams to denote a switch:

> Diagram

A switch is said to be **closed** when it completes the line of a circuit, connecting the two terminals of the switch and allowing electrons to flow through. A closed switch functions the same way as a regular circuit line:

> Diagram showing a closed switch, with arrows showing electrons flowing through

A switch is said to be **open** when you disconnect its two terminals, stopping the flow of electrons:

> Diagram showing an open switch, where electrons have nowhere to go and thus don't move

A traditional switch is mechanical: someone needs to physically move something to close it (completing the circuit) or open it (breaking the circuit). The **transistor**, a more modern cousin of the switch, does the same thing, but can be opened or closed electronically:

> Diagram showing a transistor schematic element

Transistors have three terminals: an input line, an output line and a switching line. The input and output lines work like those of a regular mechanical switch. The third switching line is used to open and close the transistor: when electricity passes through the switching line, the transistor 'closes' and allows electricity to flow from the input line to the output line. When there's no electricity passing through the switching line, the transistor prevents electricity from passing through the input line to the output line:

> Diagrams showing an open and a closed transistor

Note that electricity passing into the switching line doesn't pass to the output line. In a real transistor, there's usually a fourth line which directs the output from the switching line to a ground. We don't usually show this in schematic diagrams because it adds clutter and doesn't tell us anything useful.

Although in this book we'll treat transistors like switches as just described, note that a transistor is more than just a switch to circuit designers: what a transistor *really* does is scale how much electricity passes from the input line to the output line based on how much electricity is passing through the switching line. This allows fluctuations along the switching line to cause the same fluctuations along the input/output lines. One of the most common applications of transistors outside of computing is to [build electronic amplifiers](https://learn.sparkfun.com/tutorials/transistors/applications-ii-amplifiers).

## Digital Logic Circuits

We finally understand circuitry well enough to start building the kinds of circuits that go inside computers!

The basic idea of a digital logic circuit is to use a combination of grounding and transistors to switch transistors on and off, which in turn switches other transistors on and off, and so on, in a pattern that does something meaningful, such as adding two numbers.

Digital logic circuits are composed of digital logic **gates**, each of which is a component that does something interesting. Each gate has

* Lines that connect to a power source, providing the gate with electricity
* Lines that connect to a ground, providing the gate with a way to shed electricity
* One or more input lines, which have a meaning specific to the kind of gate
* One or more output lines, the value of which are derived from the input lines

Digital logic circuits are usually implemented by chaining logic gates together, such that the output of a gate (or a set of gates) is connected to the input of another gate (or set of gates). The result doesn't look very much like a classic electronic circuit at all, because each gate is independently connected to power and ground; instead of being interested in what happens between the terminals of our power source like in regular circuits, digital logic circuit designers are more interested in what happens along the gates' input and output lines.

For a more concrete example of a digital logic gate and what it does, consider a **binary adder** gate that takes two 8-digit binary numbers as input and outputs the sum of those two numbers as an 8-digit binary number. This gate would need lines to power and ground, plus 16 input lines (one for each digit of each 8-bit input number), and 8 output lines (one for each digit of the 8-bit output number). The input and output lines use switching to represent binary digits: a closed line (one which sends electricity) is considered to be a $1$ and an open line (where electricty doesn't flow) is considered to be a $0$.

Inside the gate, we feed the input digits into the switching lines of several transistors, which in turn switch other transistors on and off, and so on. such that each line of output corresponds to a digit of the binary sum of the two input numbers.

If this sounds really complex or even magical, turn the page to learn how simple it is to design a circuit like this!