---
layout: chapter
title: A Basic Computer&#58; Circuits
---

Modern computers are [digital circuits](https://en.wikipedia.org/wiki/Digital_electronics), which are [electric circuits](https://simple.wikipedia.org/wiki/Electrical_circuit) that are designed to operate on discrete values (in a vast majority of cases, just two: 0 and 1, binary). 

Let's start by taking a look at classical analog (non-digital) electrical circuits; this will form the basis by which we build up digital logic, calculation, and eventually, computation!

## Lines and Electricity

If you've ever popped a balloon or vented a pressure cooker, you've experienced the tendency of air to equalize differences in air pressure: if you provide a way for high-pressure air to move to lower pressure, it will &mdash; sometimes explosively!

High pressure air is just air where the atoms which make up the air are tightly packed, so another way of phrasing this tendence is that tightly-packed air will spread out if you give it room to.

Electrons, the particles that make up electricity, do something similar: if you have a bunch of tightly-packed electrons and give them roomt to spread out, they will! The goal of an electrical circuit is to use this fact to move electrons in a line, through components that use the electricity to do something.

The most basic element of a circuit is a **line** (sometimes alternately called a **wire**). This is how we normally represent lines in a **schematic diagram**, which are diagrams we use to visualize the basic construction of an electrical circuit:

> A horizontal line connecting two terminals as little circles. Label the left terminal $(-)$ and the right terminal $(+)$.

A line is a conduit which allows electrons to pass through it. Each of the two circles at the ends of the line above are called **terminals**. Terminals are connection points between elements of a circuit. 

In the diagram, we labeled one terminal $(-)$ to indicate that it is **negatively charged**, meaning it consists of densely-packed electrons that want room to expand; the other terminal is labeled $(+)$ to indicate that it is **positively charged**, meaning it consists of loosely-packed electrons and gives them room to expand. Since the line itself is a conduit for electrons, the electrons flow out from the negative terminal, where they are densely packed, expanding to fill the available space in the positive terminal. 

> If it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it sort of is.
>
> The first people to study electricity and construct circuits knew electricity was moving through the circuits, but couldn't be sure which direction it was moving, so they guessed, having a 50/50 chance of being right. It turns out they guessed wrong, but by the time we realized our notation was backwards it was already being used widely to describe existing circuits, and flipping the signs to work more intuitively would have created more confusion for existing circuits than it would have helped explain new circuits.
>
> And lo, to this day, electrons are thought to be 'negatively' charged and flow from the negative terminal to positive &mdash; oops!

There are a few key terms that circuit designers use to describe the flow of electrons through lines like these:

Any time you count electrons, that quantity is called **charge**. Charge is measured in **Coulombs**, which are abbreviated $C$.

**Current** refers to the movement of electrons. Current is measured as the rate at which electrons are moving through a medium; this rate is called **amperage**. The name derives from the corresponding unit of measurement, **amperes**, which is often shorted to just **amp** or abbreviated $A$. In the context of electrical circuits, amperage is typically used to describe the rate at which electrons pass through the circuit.

Any time you talk about the differences in charges between two points in a circuit, you inevitably end up talking about **voltage**, which like amperage is named after its unit of measurement: **volts** ($V$). Voltage is a bit tricky to define crisply without breaking out the math, but it effectively measures the degree electrons 'want' to move from one point in the circuit to another, like measuring the differences in air pressure that causes air to want to move (i.e. from higher pressure to lower pressure).

Since a voltage desribes a difference between two points, you always need two different points on a circuit to begin talking about voltages (and you say that you're measing the voltage *between* those points). We often talk about voltages between two terminals of a line in a circuit, so for brevity we often refer to a line's "voltage," even though what we really mean is the voltage between the two terminals the line connects.

Voltage and current are innately realted: increasing a line's voltage (that is, the voltage between the line's terminals) causes amperage to rise proportionally, because the additional voltage 'pressure' pushes more electrons through the wire faster. However, amperage also depends on aspects of the line itself: basically, 'thinner' lines accommodate less current for a given voltage than do 'thicker' lines.

As an analogy, imagine water being pushed through a straw or a sewer main. For either, the amount of water pouring at the end depends on the pressure of water being pushed in; but, for any given water pressure, much less water pours out the straw than the sewer main, because the straw gives the water much less room to flow. The water pressure is analogous to voltage, and the amount of water pouring out is analogous to amperage.

## Circuits and Power Sources

Now that we understand the basic principles by which electriicty moves through circuitry, it's time to start working with full circuits. To do this, we need to add another element: a **power source**. Here's how we show power sources in a schematic diagram:

> Diagram showing a power source by itself, with its terminals labeled $(+)$ and $(-)$

The basic job of a power source is to provide two terminals with a voltage between them. The negative terminal consists of densely packed electrons, and the positive terminal consists of relatively less densely packed electrons.

By connecting these two terminals together, we allow electrons to flow from the negative terminal to the positive terminal, creating our very first circuit:

> Diagram

As we can see in the diagram above, the name 'circuit' comes from the fact that the lines in a circuit form a loop. All we need to do now is to invent some other interesting components that do something when current passes through them, and add them to our circuit such that the power source's voltage 'pull's electrons through them.

## Junctions and Grounding

The first component we're going to add to our circuit is called a **ground**, which is denoted using the following symbol in circuit schematics:

> Diagram showing a ground by itself

In essence, a ground is a soak for electrons, providing them with nearly infinite room to expand. As such, the voltage between any point in the circuit and the ground is nearly infinite. To make the math easier, we often approximate this voltage as being literally infinite.

Grounds are named that way because they are often implemented by literally connecting a wire to the ground. the Earth has a lot of atoms and is not electrically charged, which means it has the ability to soak up very large number of electrons at a very high rate, effectively acting as a sink to soak up electrons provided by a power source. This is why the element is called a ground, as well as why the act of sending current to a ground called "grounding."

There's just one problem with the grounding element: it only has a single terminal. How do we add a ground to our circuit, forming a full loop between both terminals of the power source, while still also connecting the ground to the circuit? To do this, we'll need to introduce our first **junction**:

> Diagram showing a line which splits in two at a junction

A junction is just a point at which lines are connected together. In terms of the flow of current, a junction typically either splits one line into multiple lines, or merges multiple lines into a single line:

> Diagrams showing both conditions

The amount of current that flows through a junction is a constant; so, for example, in a junction that splits current among multiple lines, the total amperge passing through the output lines is equal to the amperage entering through the input line. The portion of the current that passes through each line depends on the lines' relative voltages:

> Diagram showing a junction that splits an input into two outputs, with the outputs labeled $V_1$ and $V_2$

In the diagram above, we see a junction which splits an input line into two output lines, with respective voltages $V_1$ and $V_2$. Say, for example, that $V_2 = 3 * V_1$; then, at this junction, $25\%$ of the current passes through line 1, and $75\%$ of the current passes through line 2. 

With junctions, we can now attach a grounding element to our circuit:

> Diagram showing the same basic circuit, but drain out to a ground using a junction

What happens in this circuit? Let's zoom into just the junction that we connected to the ground:

> Diagram showing the junction's input line, output line, ground line, label voltages

Remember that the purpose of a ground is to provide an 'electron sink,' such that the voltage between the input line and the ground is approximately infinite. Then we can simplify this diagram by saying the voltage at the grounding line is infinite, and by comparison, the voltage at the output line is approxmiately equal to zero:

> Same diagram, but label the voltages as infinite and zero

Since the amount of current that exits through each line of a junction is proportional to the lines' relativ voltages, we see what happens here: all current passes through the grounding line, and (effectively) no current passes through the output line.

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