---
layout: chapter
title: A Basic Computer&#58; Circuits
---

Modern computers are [digital circuits](https://en.wikipedia.org/wiki/Digital_electronics), which are [electric circuits](https://simple.wikipedia.org/wiki/Electrical_circuit) that are designed to operate on discrete values. In a vast majority of cases, these circuits operate on just two discrete values: the binary digits 0 and 1.

Let's start by taking a look at classical analog (non-digital) electrical circuits; this will form the basis by which we build up digital logic, calculation, and eventually, a computer!

## A Minimal Circuit

The goal of an electrical circuit is to set up a predictable flow of electricity, so that we can pass electricity through something that does something interesting (maybe an LED that emits light, a speaker that makes sound, and so on).

When discussing circuits, we often use a type of diagram called a **schematic**, which gives us a high level idea of how the circuit might look without getting into any of the nitty-gritty details. The following schematic describes the most basic circuit:

> Diagram with a DC source with both its terminals connected by a loop

Let's break it down:

This thing has a few names; to keep it simple, we'll call it a **power source**.

> Diagram showing just a voltage source

In real circuits, power sources like these might be provided by a battery, or an A/C adapter plugged into one of your home's power outlets. In the diagram, we see that a power source has two **terminals**: a positive terminal labeled $(+)$ and a negative terminal labeled $(-)$. 

In our example circuit above, we connected the terminals with a single **line**:

> Diagram showing just a line connecting two terminals

Lines in a circuit provide a conduit along which electricity can flow. In a real circuit, a line might be a wire made of some kind of conductive material that allows electricity to flow freely, surrounded by an insulator which prevents electricity from flowing out of the wire. In this way, a line sort of acts like a pipe, but for electricity instead of water.

Now that we understand what our power source and our line both do, let's take another look at our circuit:

> The same full diagram with a DC source connected by a loop

What does this circuit do?

To answer that, we need a basic model of how electricity works. Electricity is made up of subatomic particles called electrons, which have a tendency to repel each other. The negative terminal of our power source consists of densely packed electrons that want to repel each other, whereas the positive terminal of our power source consists of loosely packed electrons. 

> Diagram which zooms into a DC source and shows electrons as dots

As soon as we connect these two terminals with a line of our circuit, we give electrons room to move freely between the positive and negative terminals of the power source. What happens next is a sort of tug of war: all the electrons in both circuits repel each other, but the negative terminal's electrons have more oomph because of how densely packed they are. So the negative terminal 'wins' the tug of war, sending electrons over to the positive terminal through the line we connected them using:

> Diagram of the original terminal, but with arrows showing the direction electricity flows

This process will continue until the negative and positive terminals end up with the same electron densities. At this point, both terminals have the same repulsive force, and nobody wins the tug of war (it's a stalemate):

> Diagram showing the equilibrium state of the battery

This is why your phone or laptop's battery eventually runs out of charge: once both terminals of the battery have equalized, there's nothing to push electrons through the circuit anymore. You need to recharge your battery (doing work to push electrons from the positive terminal back into the negative terminal) to restart the process.

> By the way, if it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it sort of is.
>
> The first people to study electricity and construct circuits knew electricity was moving through the circuits, but couldn't be sure which direction it was moving, so they guessed, having a 50/50 chance of being right. It turns out they guessed wrong, but by the time we realized our notation was backwards it was already being used all over the place, making it too late to switch back to a more intuitive system.
>
> And lo, to this day, electrons are thought to be 'negatively' charged and flow from the negative terminal to positive &mdash; oops!

## Grounding

Let's add another element to our circuits: the **ground**:

> Schematic icon for a ground

A ground is a circuit element that soaks up electrons. If you connect a circuit to a ground, all the electricity goes to the ground forever, instead of continuing along the circuit. This allows you to effectively 'turn off' part of the circuit:

> Schematic diagram showing the same basic loop circuit as before, but now with a ground connected via a junction. Arrows showing charge flowing from the negative terminal to the ground, with no charge moving through the side of the circuit connected to the positive circuit

At the atomic level, a ground works much in the same way as the posiive terminal of a power source: its electrons are less tightly packed than those in a power source's negative terminal, so when you connect them together, the ground 'loses' the subatomic tug-of-war, and electrons flow from the negative terminal to the ground:

> Same tug-of-war diagram as before

What makes grounding special is that the ground is typically much, much larger than the power source, so dumping electrons into the ground doesn't measurably affect how densely packed the electrons are. So the electron densities between a negative terminal and a ground never equalize the way they do between a negative terminal and a positive terminal:

> Diagram contrasting the two

This way, a ground works sort of like a universal positive terminal: it soaks up all the electrons that are connected to it. If you put a ground in between you and the negative terminal of a circuit, no electrons reach you, because they all get pushed into the (large, roomy, not densely packed) ground instead:

> Diagram

## Switching

In digital circuits like the one we're going to build into a computer, grounds are most useful when combined with another element called a **switch**.

A switch is just a way of connecting and disconnecting a line in a circuit. We use the following symbol in schematic diagrams to denote a switch:

> Diagram

A switch is said to be **closed** when it completes the line of a circuit, connecting the two terminals of the switch and allowing electrons to flow through. A closed switch functions the same way as a regular circuit line:

> Diagram showing a closed switch, with arrows showing electrons flowing through

A switch is said to be **open** when you disconnect its two terminals, stopping the flow of electrons:

> Diagram showing an open switch, where electrons have nowhere to go and thus don't move

A traditional switch is mechanical: someone needs to physically move something to close it (completing the circuit) or open it (breaking the circuit). The **transistor**, a more modern cousin of the switch, does the same thing, but can be opened or closed electronically:

> Diagram showing a transistor schematic element

Transistor each have three terminals. The input and output terminals of a transistor work the same way as the two terminals of a switch: when the transistor is 'closed,' current is able to flow from the input terminal to the output terminal, but when the transistor is 'open,' current cannot flow between the two terminals.

The third 'switching' line of the transistor determines which state the transistor is in: sending current through the switching line closes the transistor, allowing current to flow. If no current is sent through the switching line, the transistor is open, and current does not pass through the transistor's input and output lines. 

> Diagram showing the same transistor twice, with current flows bolded. In one case, current is sent through the switch line and the input line, causing current to flow; in the other, current is sent to the input line but not through the switching line, so there is no current at the output line

## Digital Logic

In the next chapter, we'll explore how to we can use electrical circuits consisting of transistors and grounding elements to build a calculator, which we will later make into a full-blown programmable computer.