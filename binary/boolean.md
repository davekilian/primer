---
layout: chapter
title: Binary&#58; Boolean Math
---

It turns out you can do some pretty interesting math with single-digit binary numbers &mdash; that is, using just the numbers of $0$ and $1$. On this page, we're going to learn a little about that math.

Whenever we need to do math on a single-digit binary number in a computer, we use the **boolean** framework, which is named after George Boole, who outlined it in the mid-1800s. Note that the first electronic computer didn't come about until the mid-1900s or so; so what was Boole doing with binary numbers a hundred years before we needed them for computers?

The answer is simple: Boole wasn't studying computers; he was studying logic!

## Logic

Logic is a way of getting information about the world. You start with a set of facts you know (or assume) to be true, and you use logic to derive new facts that you didn't already know. Each of those starting facts is called a **premise**, and the fact you derive from the premises is called a **conclusion**. A set of premises which imply a conclusion is called a logical **argument**.

Sounds pretty abstract, huh? Here's an example:

Imagine you had a teacher who, as a rule, would always bring in an umbrella any day there was rain in the forecast, but never on days when the forecast was dry. Let's also say that, today, your teacher brought in am umbrella. What does that tell you? Of course: there must be rain in the forecast today!

In this example, the *premises* of the logical argument are ...

* Your teacher brings in an umbrella when rain is in the forecast
* Your teacher does not bring in an umbrella when rain is not in the forecast
* Your teacher brought in an umbrella today

The *conclusion* is: there is rain in the forecast today. Put it all together, and you have a logical argument!

The framework for logical arguments we just learned originally came out of philosophy. Like most philosophy, logical arguments were thus written down in an essay format. Representing logic in writing can be kind of messy though! Writing is ambiguous, especially when a text has to be translated from the writer's native language to another language. Plus, if you're putting a logical argument in words, it has to be short enough to fit into someone's head. Is there a better way to represent logic?

Boole certainly seems to have thought so. He invented a mathematical notation system for representing and manipulating logical arguments. In theory, this should help represent logical arguments unambiguously, without the need to translate texts, and maybe even allow us to work with very large and complex logical arguments! And, of course, 100 years later we found Boole's logic notation system to be very useful for doing math in computers. 

Since it's so useful in computing, let's learn a little about how Boole's system works.

## Boolean Logic

First, in boolean logic, every statement is either `true` or `false`. To keep it simple, Boole did not leave room for half-truths or partial correctness! When we think about boolean math from a logical perspective, we often use the terms "true" and "false" as mentioned above; but when we write it down notationally, we often use the binary digits $0$ and $1$ instead:

| Boolean Value | Binary Value |
| ------------- | ------------ |
| `false`       | $0$          |
| `true`        | $1$          |

In modern parlance, a **boolean value** is one of the items in the table above: if you choose to use the logical notation, then a boolean value is either `true` or `false`; if you choose to use the binary notation, a boolean value is a single binary digit: $0$ or $1$. Both notations are equally valid.

By the way, if you remember our discussion of binary and binary math on the previous page, there's our link between boolean math and single-digit binary numbers: a boolean value can be $0$ or $1$, just like a single digit in binary! So whatever we can do on boolean values, we can also do on single-digit binary numbers.

But, what are those things? What logial operations did Boole define over the boolean values `true` ($1$) and `false` ($0$)?

## Not

The simplest of Boole's logical operation was negation, which is usually pronounced "not." The negation operation just produces the opposite of the given value.

For example, let's consider the logic statement, "it is raining." Negation gives us the opposite statement: "it is <ins>not</ins> raining." Clearly these statements are opposites: if one is true, then the other must be false!

Let's use Boole's notation system to represent this mathematically:

Let the boolean value $R$ represent the statement "it is raining." If it is actually raining right now, then $R$ is `true` ($1$); if it's dry outside, then $R$ is instead `false` ($0$).

To negate $R$ and obtain its opposite, we use the $\neg$ operator. So $\neg R$ is the opposite of $R$: since $R$ means "it is raining," $\neg R$ Means, "it is <ins>not</ins> raining."



> Computing notation: `~` and `!`
>
> Truth table

## And

> The two names
>
> Example based on logic
>
> Mathematical notation $\and$ 
>
> Computing notation: `&`
>
> Truth table

## Or

> The two names
>
> Example based on logic
>
> Mathematical notation $\or$
>
> Computing notation: `|`
>
> Truth table

## Exclusive-Or

> The two names
>
> Example based on logic
>
> Mathematical notation $\oplus$
>
> Computing notation: `^`
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

## Booleans and Binary

> We need to tie back true/false to 0/1 again

## Preview: Logic Gates

> Tie it all back by previewing logic gates: the simplest of transistor networks implement operations like NOT, AND, OR and XOR. The rest of the math we will later build in circuitry will be built using networks of logic gates, not by messing with transistors directly.

