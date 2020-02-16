---
layout: chapter
title: A Basic Computer&#58; Circuits
---

Modern computers are [digital circuits](https://en.wikipedia.org/wiki/Digital_electronics), which are [electric circuits](https://simple.wikipedia.org/wiki/Electrical_circuit) that are designed to operate on discrete values. In a vast majority of cases, these circuits operate on just two discrete values: the binary digits 0 and 1.

Let's start by taking a look at classical analog (non-digital) electrical circuits; this will form the basis by which we build up digital logic, calculation, and eventually, a computer!

## A Minimal Circuit

The goal of an electrical circuit is to set up a predictable flow of electricity. 











---

## Analogy for Electricity

> In this chapter, we will use a simple metaphor involving air pressure to help explain the physics of how electricity works, especially in circuits. Although this metaphor will work for everything we're going to do with circuits, it's not a perfect metaphor, which is why you don't usually see electrical engineers use it.
>
> If you like this discussion and want to learn a more correct (but somewhat harder to think about) metaphor for electricity in circuits, check out the [hydraulic analogy for electricity](https://en.wikipedia.org/wiki/Hydraulic_analogy) sometime.

If you've ever popped a balloon or vented a pressure cooker, you've experienced air's tendency to equalize in pressure. If you provide a way for high-pressure air to move to lower pressure, it will &mdash; sometimes explosively!

> Diagram

High pressure air is just air where the atoms which make up the air are tightly packed, so it'd be equally valid to describe this phenomenon by saying tightly-packed air will spread it out if you give it room to:

> Diagram

Electrons, the particles that make up electricity, do something similar: if you have a bunch of tightly-packed electrons and give them room to spread out, they will! The goal of an electrical circuit is to take advantage of this by giving a group of tightly packed electrons a single path on which to spread out. Because the electrons tend to spread out, they end up moving down this path:

> Diagram

We can then put something along this pack and make the electrons flow through it to do something interesting:

> Diagram

## Lines in a Circuit

The most basic element of a circuit is a **line** (sometimes instead called a **wire**). This is how we normally represent lines in a **schematic diagram**, which are diagrams we use to visualize the overall structure of an electrical circuit:

> A horizontal line connecting two terminals as little circles. Label the left terminal $(-)$ and the right terminal $(+)$.

A line is a conduit which allows electrons to pass through it. Each of the two circles at the ends of the line above are called **terminals**. Terminals are connection points between elements of a circuit. 

In the diagram, we labeled one terminal $(-)$ to indicate that it is **negatively charged**, meaning it consists of densely-packed electrons that want to expand, and will if given room; the other terminal is labeled $(+)$ to indicate that it is **positively charged**, meaning it consists of loosely-packed electrons. The line itself provides a path for electrons at the (dense) negative terminal to move to the (roomy) positive terminal.

> If it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it sort of is.
>
> The first people to study electricity and construct circuits knew electricity was moving through the circuits, but couldn't be sure which direction it was moving, so they guessed, having a 50/50 chance of being right. It turns out they guessed wrong, but by the time we realized our notation was backwards it was already being used all over the place, making it too late to switch back to a more intuitive system.
>
> And lo, to this day, electrons are thought to be 'negatively' charged and flow from the negative terminal to positive &mdash; oops!

There are a few key terms that circuit designers use to describe the flow of electrons through lines like these:

Any time you count electrons, that quantity is called **charge**. Charge is measured in **Coulombs**, which are abbreviated $C$.

**Current** refers to the movement of electrons. Current is measured as the rate at which electrons are moving through a medium; this rate is called **amperage**. The name derives from the corresponding unit of measurement, **amperes**, which is often shorted to just **amp** or abbreviated $A$. In the context of electrical circuits, amperage is typically used to describe the rate at which electrons pass through a line in a circuit.

Any time you talk about the differences in charges between two points in a circuit, you inevitably end up talking about **voltage**, which like amperage is named after its unit of measurement: **volts** ($V$). Voltage is a bit tricky to define without breaking out math, but it effectively measures the degree to which electrons 'want' to move from one point in the circuit to another. Using our analogy with air pressure, voltage measures something like a difference in air pressure, but for electrons.

Since a voltage desribes a difference between two points, you always need two different points on a circuit to begin talking about voltages (and you say that you're measing the voltage *between* those points). It's common to describe a line as having a "voltage," but this is a shortcut for talking about the voltage between the two terminals the line connects:

> Diagram

If you want to go on to design circuits, you'll eventually need to learn about some important relationships between voltage and current. However, since we're interested in digital circuits in this book, we can confine ourselves to worrying about voltages across a line of the circuit: as circuit designers, we pick a voltage threshold such that lines with a voltage above this threshold are considered to hold a binary $1$, and lines below this threshold are considered to hold a binary $0$:

> Diagram

## Circuits and Power Sources

Now that we understand the basic principles by which electriicty moves through circuitry, it's time to start working with full circuits. To do this, we need to add another element: a **power source**. Here's how we show power sources in a schematic diagram:

> Diagram showing a power source by itself, with its terminals labeled $(+)$ and $(-)$

The basic job of a power source is to provide two terminals with a non-zero voltage between them. Like before, the negative terminal consists of densely packed electrons, and the positive terminal consists of more loosely packed electrons. By connecting these two terminals together with a line, we allow electrons to flow from the negative terminal to the positive terminal, creating our very first circuit:

> Diagram

As we can see in the diagram above, the name 'circuit' comes from the fact that the lines in a circuit form a loop. All we need to do now is to invent some other interesting components that do something when current passes through them, and add them to our circuit, so that the use the power source's voltage to 'push' electrons through these new components.

## Junctions and Grounding

The first component we're going to add to our circuit is called a **ground**, which is denoted using the following symbol in circuit schematics:

> Diagram showing a ground by itself

In essence, a ground is a soak for electrons, providing them with nearly infinite room to expand. As such, the voltage between any point in the circuit and the ground is nearly infinite. To make the math easier, we often even approximate this voltage as being literally infinite.

Grounds are named that way because you often make one by literally connecting a wire to the ground (the thing you walk on). The Earth has a lot of atoms and is not electrically charged, which means it has the ability to soak up very large number of electrons at a very high rate, effectively acting as a sink to soak up electrons provided by a circuit line. This is why the element is called a ground, as well as why the act of sending current to a ground called "grounding."

There's just one problem with the grounding element: it only has a single terminal. How do we make a circuit that forms a full loop while still including a connection to a ground? To do that, we'll need to invent the **junction**:

> Diagram showing a line which splits in two at a junction

A junction is just a point at which lines are connected together at the same terminal. Depending on the direction current is flowing, the result is usually to either split an "input" current across multiple "output" lines, or join multiple inputs to a single output:

> Diagrams showing both conditions

The amount of current that flows out of a junction always has to be equal to the amount of current that flows into a junction, becuase there's nowhere else for the current to go. So, if an example junction were to split a current among multiple lines, summing the output lines' amperages should always equal the input line's amperage.

For us, the key rule for designing junctions will involve voltages: when you split a line into multiple lines at a junction, the amount of current that goes into each output is proportional to each line's output voltage:

> Diagram showing a junction that splits an input into two outputs. The input terminal is labeled $A$ and the output terminals are labeled $B$ and $C$. Label the line that terminates in $B$ "line 1," and name the other one "line 2."
>
> Redo the paragraph below to define the different voltages as $V_{AB}$ and $V_{AC}$ to make it clear what we're measuring when we say it's proportional.

---

In the diagram above, we see a junction which splits an input line into two output lines, with respective voltages $V_1$ and $V_2$. Say, for example, that $V_2 = 3 * V_1$; then, at this junction, $25\%$ of the current passes through line 1, and $75\%$ of the current passes through line 2. 

With junctions, we can now attach a grounding element to our circuit:

> Diagram showing the same basic circuit, but drain out to a ground using a junction

What happens in this circuit? Let's zoom into just the junction that we connected to the ground:

> Diagram showing the junction's input line, output line, ground line, label voltages

Remember that the purpose of a ground is to provide 'infinite' voltage between the input line and the output line. So we can simplify this diagram by saying the voltage at the grounded line is infinite, and by comparison, the voltage at the output line is approxmiately equal to zero:

> Same diagram, but label the voltages as infinite and zero

Since the amount of current that exits through each line of a junction is proportional to the lines' relative voltages, we see what happens here: *all* the current passes through the grounding line, and (effectively) no current passes through the output line.

> The original circuit-with-ground diagram, but bold the lines to show that all the current has passed to the ground

We essentially drained the current out of the circuit. It may not be obvious right now why this is useful, but keep this in your back pocket - we'll use it again later.

## Switches and Transistors 

The final circuit element we'll need in building our computer is the switch, as well as its more modern cousin the transistor.

A **switch** is an element that can be used to disconnect and reconnect a line in a circuit. Switches are denoted using the following symbol:

> Diagram

Switches have two states. A **closed** switch is one which 'completes' the line of the circuit, connecting the two terminals of the switch and allowing electrons to flow through. A closed switch functions exactly the same as a wire. An **open** switch, on the other hand, disconnects the two terminals, thereby preventing electrons from passing through.

Switches are traditionally mechanical, meaning that someone or something has to physically toggle a switch in order to open or close it. The **transistor**, a more modern cousin of the switch, does the same thing, but can be opened or closed electronically:

> Diagram showing a transistor element

As we see in the diagram above, each transistor consists of three terminals. The input and output terminals of a transistor work the same way as the two terminals of a switch: when the transistor is 'closed,' current is able to flow from the input terminal to the output terminal, but when the transistor is 'open,' current cannot flow between the two terminals.

The third 'switching' line of the transistor determines which state the transistor is in: sending current through the switching line closes the transistor, allowing current to flow. If no current is sent through the switching line, the transistor is open, and current does not pass through the transistor's input and output lines. 

> Diagram showing the same transistor twice, with current flows bolded. In one case, current is sent through the switch line and the input line, causing current to flow; in the other, current is sent to the input line but not through the switching line, so there is no current at the output line

The transistor is the foundational circuit element in modern computers; the invention of the transistor allowed us to create reasonably small, cost-effective computers and can arguably be said to have driven the computing revolution. In fact, [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law), which we mentioned in a previous chapter, specifically measures the progress of computer hardware manufacturing as the number of transistors we can fit in a given space &mdash; for a long time now, we've managed to roughly double this value every two years.

In the next chapter, we'll explore how to we can use electrical circuits consisting of transistors and grounding elements to build a calculator, which will become the internal calculator that drives our programmable computer.