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

A power source is anything that induces the flow of electricity. In the real world, a power source might be a battery, or a generator. In schematic diagrams, each power source is shown with two terminals, labelled $-$ ("negative") and $+$ ("positive"). When you connect these two terminals together, electricity flows from the negative terminal to the positive terminal:

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

## Junctions

Now we understand the basic elements of a circuit and how electricity moves through a circuit. To build a calculator, we still need a few more circuit components. The next component we'll examine isn't technically a component by common definition, but we still need to understand nonetheless.

A junction is point in a circuit where two or more terminals are connected together. We've already seen junctions in our minimumal circuit earlier: there were junctions at each terminal of the battery, connecting each battery terminal to one of the wire's terminals:

> Diagram of the min viable circuit again, but circle the junctions

Two-way junctions are so simple they aren't worth discussing; things get more interesting once a junction connects three or more terminals at once. For example, here's our minimal circuit again, but with an extra line split out and later merged back in at junctions $1$ and $2$ respectively:

> Diagram of our minimal circuit from before with two junctions labeled 1 and 2 where the line splits into two output lines (junction 1) and then those line merge into the final output line (junction 2). Label the two lines that get split and re-merged A and B

Junctions $1$ and $2$ in this diagram are both three-way junctions: they each connect three different lines together. Junction $1$ splits a single input line (providing electricity) into two output lines $A$ and $B$ (receiving electricity from the junction). The total amount of electricity is preserved, and since there are two output lines, each carries half the electricity received from the input line. Meanwhile, junction $2$ merges input lines $A$ and $B$ back together, sending all the resulting electricity along the output line back to the battery terminal. No electricity was added or removed along the way; we just divided up the electricity at junction $1$ and merged it back together at junction $2$.

To understand why junctions work this way, we need only go back to our discussion of a tug-of-war from the previous heading. A three-way junction is like a three-way game of tug-of-war between electrons. At junction $1$, the input line has electrons coming from the negative battery terminal, whereas the output lines have in total as much electricity as is being pushed out of the battery's positive terminal. We've seen the rest of this story already: the negative terminal's electrons are pushing much harder and win the tug of war, advancing down the junction's output lines. Since each line is as good as the other 

> Diagram of the tug-of-war in junction 1

The story is similar at junction 2. Here we have two input lines with electrons that ultimately came from the negative terminal; and one output line with electrons that ultimately came from the positive terminal. The negative terminal electrons push harder, all merging together to travel down the output line:

> Diagram of the tug-of-war in junction 2

An interesting question is, what would happen if we added a three-way junction that splits an input line into multiple output lines, but one of those output lines were a dead end that didn't go anywhere? Like this:

> Diagram where we've removed junction 2, such that line $A$ connects to the battery but $B$ doesn't go anywhere. To avoid confusion, we'll change the name of junction 1 to junction 3

What happens at our new junction, junction $3$?

Initially, when you turn on the circuit, junction $3$ behaves a lot like junction 1: there's a single input line pushing electricity into the junction, and two output lines, $A$ and $B$, where electricity can flow; so electricity flows along each output line:

> Diagram showing the initial state again

However, now that line $B$ isn't connected to the battery's positive terminal, so once electrons go into line $B$ there's no way for them to leave. So line $B$ immediately fills up with electrons, which then start *pushing back* into junction $3$, like this:

> Diagram showing junction 3 with $B$ pushing back at 

Once line $B$ has 'filled up' with electrons (which takes almost no time at all), the electron density inside line $B$ is the same as in the battery's negative cell, so no more electrons win the tug-of-war needed to enter line $B$. With no electricity flowing in or out of $B$, we end up in a steady state where all electricity moves from the input line to output line $A$, as if line $B$ weren't connected to the junction at all.

The takeaway: if you disconnect a junction's output line from the rest of the circuit, the junction behaves as if that output line doesn't exist. This will be a super handy feature once we start building our calculator soon!

Finally, it's worth mentioning that people who design circuits use a fundamental relationship between current, voltage and resistance to describe exactly how much current flows out of a junction; but as before, we don't need to do so in this book to understand how our computers work, so we'll skip over the details.

## Grounding

Junctions get more interesting when you add another circuit component that we haven't talked about yet: the **ground**.

> Schematic icon for a ground

A ground is called a ground because you usually ground a circuit by literally connecting the circuit to the ground; the Earth is the largest and best grounding component around! Some electronics (like your phone) can't be grounded using the Earth and thus require [more complex workarounds](https://en.wikipedia.org/wiki/Floating_ground).

As a circuit component, grounds exist to soak up electricity. You can almost think of a ground as a way of pulling electrons out of a circuit: if a ground is connected to one end of a 3-way junction, all input electricity flows to the ground, leaving none to flow down the rest of the circuit

> Diagram showing electricity flowing to a ground instead of to the positive terminal of a battery

The important takeway for our discussion is that grounding can effectively 'shut off' the part of the circuit which is downstream of the junction with the ground. For example, say we added some electrical component (denoted by $?$) to our circuit like this:

> The same circuit schematic showing a new $?$ component downstream of the ground junction

In this circuit, the $?$ element doesn't receive any electricity, even though it's connected to the junction, because all electricity leaving the negative terminal of the battery travels through the junction to the ground.

From a physics perspective, grounding works kind of like adding third battery cell to your circuit. This cell has even less-densely packed electrons than either cell of the battery, so at a three-way junction that connects the battery's positve terminal, negative terminal and ground together, you get a three-way tug of war that the ground loses; so all electricity flows to the ground (from *both* battery terminals).

> Diagram showing the tug-of-war and electrons flowing from both battery terminals into the ground

At the circuit schematic level, we usually ignore the flow of electricity from the positive terminal to the ground because it's so small compared to the flow from the negative terminal.

The ground also has enormous capacity, such that no matter how long you send power to the ground, the ground's electron density doesn't change measurably. This means that a ground, unlike a battery, cannot get depleted or need to be recharged.

## Switching

In digital circuits like the one we're going to build into a computer, grounds are most useful when combined with another element called a **switch**.

A switch is just a way of connecting and disconnecting a line in a circuit. We use the following symbol in schematic diagrams to denote a switch:

> Diagram

A switch is said to be **closed** when it completes the line of a circuit, connecting the two terminals of the switch and allowing electrons to flow through. A closed switch functions the same way as a regular circuit line:

> Diagram showing a closed switch, with arrows showing electrons flowing through

A switch is said to be **open** when you disconnect its two terminals, stopping the flow of electrons:

> Diagram showing an open switch, where electrons have nowhere to go and thus don't move

An open switch behaves the same way as that orphaned line (line $B$ coming out of junction $3$) we used as an example back in the heading on junctions above.

A traditional switch is mechanical: someone needs to physically move something to close it (completing the circuit) or open it (breaking the circuit). The **transistor**, a more modern cousin of the switch, does the same thing, but can be opened or closed electronically:

> Diagram showing a transistor schematic element

Transistors have three terminals: the input and output terminals of a transistor work the same way as the two terminals of a switch: when the transistor is 'closed,' current is able to flow from the input terminal to the output terminal, but when the transistor is 'open,' current cannot flow between the two terminals. A third 'switching' line determines which state the transistor is currently in: sending electricity through the switches line 'closes' the transistor, allowing electricity to pass from the input line to the output line. If no electricity is sent to the switching line, then the transistor is 'open,' and no electricity passes from the input line to the output line.

> Diagrams showing an open and a closed transistor

Throughout this book, we will continue to think of transistors as switches. For a circuit designer, a transistor is even more than a just switch: what a transistor *really* does is scale how much electricity passes from the input line to the output line based on how much electricity is passing through the switching line. It's sort of like having a material that works as a conductor or an insulator: 

## Digital Circuits





TODO now we introduce the idea of digital circuitry and digital logic gates.

The idea: we want to have one or more 'input' lines and one or more 'output' lines. The input lines each are connected to the switching lines of one or more transistors, which then switches the transistors on or off; those transistors are connected to the switching lines of more transistors, and so on. To make this work, we'll need a power source and a ground, but those aren't the stars of the show; they're just basic tools we need to move electrons through the system.

We then set up this circuit so that which lines are on and off are meaningful. For example, we might build a binary adder where the input lines can be interpreted as two binary numbers (lack of electricity is $0$ and flowing electricity is $1$), and the output is always a sequence of (electricy / no electricity) lines that correspond to the binary number that is the sum of both. An example diagram will help a LOT here.

In a real circuit, there's no such thing as 'fully off' or 'no electricity;' even with transistors, what you have isn't a switch so much as a scaler. So with real digital circuits, you come up with a threshold; when the amount of electricity is (significantly) above the threshold the value is a $1$ and when the amount is significantly below the threshold you get a $0$. You avoid ever having values near the threshold because that increases the circuit's tendency to malfunction.

So we understand circuitry: lines, power sources, junctions, grounds, transistors and switching &mdash; so let's go build our calculator!