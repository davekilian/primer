---
layout: chapter
title: A Basic Computer&#58; Digital Logic
---

---

> This page was split out of the circuits page, and proceeds roughly as follows:
>
> * Introduce in passage the study of boolean mathematics, which deal with single digits of zeroes and ones. We're going to build a couple of boolean mathematic operations and build up to a calculator
> * First, the NOT gate, which inverts the value given: so passing in 0 to the gate (no current or voltage) causes the gate to output a 1 (current flows on its output line, due to a nonzero voltage)
> * A simple way to build a NOT gate is to take a power line and split it into a two-way junction, one of which is an output line, and the other goes to ground through a transistor. You hook up the input line to the transistor; now, when the input line is 1, the transistor switch is 'closed' and so the junction is exposed to ground, which sucks away all the charge, leaving nothing on the output line (0); when you input a 0, the transistor is now 'open' and there is no longer a path to the ground, so all voltage travels to the output gate.
> * Next we'll tackle the AND gate. Add a truth table for this
> * This one's easy: accept a power line, and pass it through two transistors, each of which is 
> * Next we'll build NAND, which is just `!(a & b)`, by passing the output of our AND gate through out NOT gate.
> * Now, if we have a way to easily stamp out / copy+paste our NAND gate on a circuit, we can use it to build a bunch of fundamental operations: AND, OR, XOR and NOT
>
> Now we're getting somewhere - it's time for multi-bit binary math. Note that we're done thinking about circuits in terms of lines, grounds, power sources and transistors: we've moved up to the 'logic' level, which concerns itself with boolean math.
>
> * Flipflops for storing values a user punched in
> * An adder
> * A shifter
> * A multiplier? or link out
> * A divider? or link out
>
> And now we have a calculator - finally time to make it programmable. Turn the page.
>

---

## Electric Circuits

The fundamental components in an electric circuit are a power source and a wire:

> Diagram of the most basic possible circuit connecting one terminal of a power source to another

These components form a loop, starting at one end of the power source and ending at the other, which is where the name "circuit" comes from. Electrons in this circuit flow from the **negative terminal** of the power source (labeled $-$ in the diagram above) to the **positive terminal** (labeled $+$)

> If it seems backwards for electrons to flow from $(-)$ to $(+)$, well, it is: the first people to study electricity and circuits guessed wrong about what direction electrons were flowing, but everyone was already using this notation by the time we figured out we had it backwards, so it ended up being too late to change it!

It's worth taking a quick look at the physics behind electrical circuits, so we can define basic terms like *charge*, *current* and *voltage*:

> cSame diagram, but now we label the terminals in terms of their potential and use arrows to show the flow of electrons

Then all that's left to do is figure out interesting things we can stick in this circuit (passing electrons through them), and stuff you accomplish by doing this (like building calculators and computers!)

Physicists and engineers who study electricity and circuits have terms to describe the flow of electrons:

Any time you count electrons, that quantity is called **charge**. Charge is measured in **Coulombs**, which are abbreviated $C$.

**Current** refers to the movement of electrons. If you want to measure the rate at which electrons are moving, you're measuring **amperage**. The name derives from the corresponding unit of measurement: **amperes**, often shortened to **amp** or abbreviated $A$. In the context of electrical circuits, amperage is typically used to describe the number of electrons which through the circuit (from the negative terminal to the positive terminal) every second.

Any time you're talking about differences in charge or current in different parts of a circuit, you inevitably end up talking about **voltage**; like with amperage, the name 'voltage' comes from the unit of measurement: **volts** ($V$). Voltage is a bit tricky to define crisply, but it effectively measures the tendency of electrons to move from one point to another, like measuring the differences in air pressure that causes air to want to move from higher to lower pressure.

You always talk about voltage *between* two points, which on a circuit, means the voltage between two circuit elements connected by a wire. We often talk about voltages of or along wires in a circuit, for brevity, when what we really mean is the voltage between the two things the wire connects. For example, in the simple example circuit from the beginning of this section, there's a nonzero voltage between the negative and positive terminals of the power source; if that voltage is $V$, then we say there's a voltage of $V$ along the only wire in our circuit:

> Same diagram, but label the wire with a voltage $V$ 

Voltage becomes important in circuit design once you start talking about **junctions**, which are points in the circuit where one wire splits, or multiple wires join:

> Diagram

At a junction that splits one wire into multiple output wires, how is charge distributed? One simple thing we can say is there are only so many electrons passing through the input line per second, so the total current among all the output wires must equal that of the input wire. 









In general, increasing the voltage of a circuit's power source causes the amperage to rise, because the additional 'pressure' pushes more electrons through the wire faster. However, the amperage also depends on the absolute level of charge at each terminal of the power source: adding more charge while keeping the voltage the same also increases amperage.

Based on this relationship between voltage and amperage, we now see what happens when you split a wire in a circuit into two:

> Diagram showing a wire on the left split into two wires on the right, labeling each wire with a voltage $V_1$ and $V_2$ 

In this situation, each output gets a share of the electrons passing through the input wire, and each wire's share is proportional to the wire's voltage. So, if $V_2 = 3 * V_1$, then $1/4$ of the current will pass through wire 1, and the other $3/4$ passes through wire 2.

If $V_2$ is much, much greater than $V_1$, then pretty much all of the current will pass through $V_2$. Circuit designers routline use this fact by hooking up a wire to another type of circuit element called a **ground**:

> Same diagram, but now wire 2 is hooked up to a ground

A ground has no charge, and have a very large amount of room for electrons to expand into; as such, the voltage between the negative terminal of the power source and the ground is enormous, causing all of the current to run to the ground (wire 2) and approxmiately not to run through the other fork in the split (wire 1).

We will use this phenomenon later while designing our calculator.

To summarize our understanding of circuits so far, we defined:

* A **power source** with a **positive terminal** and a **negative terminal**, with a voltage between the terminals
* A **wire**, sometimes called a **line**, which provide a path for electrons to flow
* A **circuit**, which consists of at least one power source, and connects everything into a loop using wires
* A **junction**, which either splits an input line into one or more output lines or joins one or more input lines into a single output line
* A **ground**, which provides a very large capacity to soak up electrons, such that the voltage between the ground and anything connected to it is effectively infinite

Feeling good with circuits so far? Then let's kick it up a notch:

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

> Define boolean not, and as the 'fundamental' mathematical operations of a digital circuit
>
> Start with a not gate: basically, a line that forks in two, one heading towards the output and one heading towards a ground. The line heading toward a ground is mediated by a transitor, which recieves the input line. So when input is high, the transitor is open, and the current drains to ground, meaning the output is low. And when the output is low, the current has nowhere to go but the output line, so the output is high. That's a not gate. 
>
> We also need a diagram. There's a good diagram on this page: https://www.instructables.com/id/Logic-Gates-with-NPN-transistors/
>
> Then and, which is an input line which passes through two inline transistors to reach an output line - both transistors must be on for current to pass from the input line to the output line. Again, a good diagram for reference: https://www.instructables.com/id/Logic-Gates-with-NPN-transistors/
>
> Now you actually have enough to build everything else: https://en.wikipedia.org/wiki/NAND_logic
>
> With our newfound gates we can now zoom out to the logic level, looking at circuits as a sequence of logic gates and no longer worrying about lines, grounds, power sources and so on. In fact, you could even build a logic circuit out of something other than electrical charges and impulses. Link to a water computer or something.

## A Digital Calculator

> Define the not, and, or, xor gates we defined above as 'boolean' math, which deals with single digits of binary (that is, 0s and 1s, sometimes alternately called `true` (1) and `false` (0).).
>
> It turns out we can use these to implement basic arithmetic on multi-digit binary numbers.
>
> Build an adder, maybe a multiplier? maybe a shifter?
>
> Build flipflops and maybe SRAM? for storing the numbers you want to input, and the numbers you want to output
>
> We just built a set of digital circuits that can calculator, but it's not programmable yet, so on to the next page.
