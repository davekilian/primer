---
layout: chapter
title: Binary&#58; Boolean Math
---

Let's think about the most basic form of math you can do on binary numbers: the math of single-digit binary numbers. In other words, this is math that only uses the numbers $0$ and $1$.

Can you do anything interesting with so little to work with? It turns out, yes!

In computing, when we need to do single-digit binary math, we usually use the **boolean** framework named after George Boole, who outlined it in the mid-1800s.

## Boolean Logic

Boole was interested in the study of logic. In logic, you take a set of facts, and you use them to derive new facts. For example, say you know your boss never brings in an umbrella unless there's rain in the forecast today, and you also know your boss brought in an umbrella today. Using these facts, you can logically derive a new fact: there must be rain in the forecast today!

Specifically, Boole was interested in representing this kind of logic mathematically. Maybe, by making it possible to write down logic operations on paper, we'd be able to work through them mathematically on paper rather than keep it all in our heads. We could potentially work through larger, tougher logic more accurrately!

Here's how Boole's system (which we'd today call boolean math) worked:

First, in boolean logic, every statement is either `true` or `false`. For simplicitly, Boole did not leave room for half-truths or partial correctness! When we think about boolean math from a logical perspective, we often use the terms "true" and "false" as mentioned above; but when we write it down notationally, we often use the binary digits $0$ and $1$ instead:

| Boolean Value | Binary Value |
| ------------- | ------------ |
| `false`       | $0$          |
| `true`        | $1$          |

In modern parlance, a **boolean value** is one of the items in the table above: if you choose to use the logical notation, then a boolean value is either `true` or `false`; if you choose to use the binary notation, a boolean value is a single binary digit: $0$ or $1$. Both notations are equally valid.

What can we do with boolean values? What logical operations did Boole define?

## Not

The "NOT" operation, also known as "negation," is the only boolean operation you can do on a single boolean value. All it does is give the opposite: `NOT(true)` is `false` and `NOT(false)` is `true`.

From a logical perspective, the NOT operation is used when you want to talk about the opposite of something happening. For example

> Example based on logic
>
> Mathematical notation
>
> Truth table

## And

> The two names
>
> Example based on logic
>
> Mathematical notation
>
> Truth table

## Or

> The two names
>
> Example based on logic
>
> Mathematical notation
>
> Truth table

## Exclusive-Or

> The two names
>
> Example based on logic
>
> Mathematical notation
>
> Truth table

## Other Operations

> Unlike the above, these rarely show up in the construction of computers, so we won't delve too deeply
>
> Implies and equivalence
>
> --
>
> The two names
>
> Example based on logic
>
> Mathematical notation
>
> Truth table

## Compund Statements

> The 'meat' of Boole's framework comes from *combining* these operations.
>
> Some of the operations above can be decomposed into compound statements of lower-order operations. Do xor, implies, equivalent.
>
> Possible to rewrite a compound statement as a different, equivalent compound statement. This is the basis of Boolean algebra. (Is it? Confirm pls)
>
> Example: De Morgan's law is a classic.

## Logic Gates

> Tie it all back by previewing logic gates: the simplest of transistor networks implement operations like NOT, AND, OR and XOR. The rest of the math we will later build in circuitry will be built using networks of logic gates, not by messing with transistors directly.

