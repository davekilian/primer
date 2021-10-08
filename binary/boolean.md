---
layout: chapter
title: Binary&#58; Boolean Math
---

> Let's think about the most basic form of math on binary numbers: math on single-digit binary numbers.
>
> In other words, this is math that only uses the numbers $0$ and $1$.
>
> Can you do anything interesting with so little? It turns out yes!
>
> George Boole first published a book in this area in (year).
>
> Boole was interested in the study of logic.
>
> Logic is when you take a set of facts, and derive new facts from them. 
>
> Example
>
> Boole was interested in representing logic mathematically. The hope was to make it easier to reason about complex logical operations by writing them down and working through them mathematically, rather than hold it all in your head.
>
> In Boole's model, every statement is either "true" or "false." Boole did not leave room for half-truths or partial correctness! In Boolean mathematics, a Boolean value can either be represented as "true/false" or equivalently, as a single binary digit: $0$ or $1$.
>
> Table mapping true/false to binary 1/0
>
> Boole then went and thought up some logical operations you could do on these true/false or 1/0 values.
>
> There's one thing you can do on a single Boolean value by itself: not. Truth table.
>
> If you have two boolean values, there are more things you can do.
>
> And: true when both input values are true; false otherwise. Truth table.
>
> Or: true when any input value is true; false otherwise. Truth table.
>
> Exclusive-or: true when the input values differ; false otherwise. Truth table
>
> All of these operations will be useful when we start thinking about how to implement math in circuitry. There are a few additional operations that aren't typically all that useful in computers, but bear mentioning here for completeness:
>
> Does-imply: when $a$ is true, this is true if $b$ is also true. When $a$ is false, this is always true. Truth table.
>
> Equivalent: $a \equiv b$ means the two always have the same value. Truth table
>
> Boole found that you could combine these operations into *compound* statements. Example
>
> Some of the operations above can be decomposed into compound statements. Do xor, implies, equivalency.
>
> Once you have a compound statement, there are often ways to transform the statement that can help simplify it.
>
> De Morgan's law is notable
>
> Tie it all back by previewing logic gates: the simplest of transistor networks implement operations like NOT, AND, OR and XOR. The rest of the math we will later build in circuitry will be built using networks of logic gates, not by messing with transistors directly.