---
layout: chapter
title: Binary&#58; Boolean Math
---

Let's talk about the math you can do with a single binary digit. Although $0$ and $1$ might seem like very little to work with, they turn out to be just enough to start doing some interesting stuff!

The mathematical framework we use to operate on single-digit binary numbers is known as **Boolean** logic, named after its original inventor, George Boole. Boole first published his conception of this framework in the mid-1800s, nearly a hundred years before we started trying to build computers using electrical circuitry. What was Boole doing with binary numbers a hundred years before we needed them for computing?

Simple: Boole wasn't studying computers. He was studying logic!

## Logic

Logic is our way of learning new things about the world from things we already know. In theory, when we use logic correctly, we can learn something new about the world *without* any sort of direct oberservation.

Sound sort of abstract? It's easier with an example.

Let's say you're in school, and you have a particular teacher who brings in an umbrella according to this rule: If there is rain in the forecast today, then your teacher brings in an umbrella; otherwise, your teacher does not bring in an umbrella. Let's also say your teacher brought in an umbrella today &mdash; logically, then, you conclude that there must be rain in the forecast today!

The key is that you 'figured out' there's rain in the forecast today, using other things you knew about the world &mdash; you did not have to check the forecast yourself!

You and I use logic all the time without realizing it. Our ancestors did too. The first people to formally study logic were philosophers, who wanted to use logic to better understand the world &mdash; and were formally studying logic to understand its strengths and weaknesses as a tool for understanding. Today, we owe these philosophers our current understanding of how logical arguments are formed, and strategies we can use to evaluate them.

Boole was also interested in studying logic, but took a different tack: what if we could represent logic using mathematical notation? While few can say what exactly compelled him to do this, it's worth noting that, traditionally, philosophers have been accustomed to presenting logical arguments using spoken and written language; coming up with a mathematical framework could theoretically allow us to work with bigger, more complex arguments, as well as make it easier to translate logical arguments between different spoken and written languages.

Whatever his reasons were, his framework became well enough known in mathematics to be expanded and improved upon, giving us the Boolean math we're accustomed to using today. Then, in the early 1900s, an electrical engineer named Claude Shannon figured out a way of using Boolean's framework in electricial circuitry, leading us into the kinds of computers we know today.

## Boolean Math

Let's take a quick look at Boolean mathematics, as we know it today. Since this is a book about building computers, we'll focus only on what we need for computing.

Boolean math is used to represent logical relationships between statements. In the example above, these logical statements might include "my teacher brought in an umbrella today" or "there is rain in the forecast today."

In Boolean logic, every statement must either be true or false. To keep the system simple, there is no room for half truths or partical correctness! "True" and "false" are called the **Boolean values**. All Boolean math operates on just these two Boolean values.

When we write down a Boolean value, we have two options: we can use the words "true" and "false," or we can use the numbers $1$ and $0$, where $1$ means "true" and $0$ means "false:" 

| Boolean Value | Binary Value |
| ------------- | ------------ |
| `false`       | $0$          |
| `true`        | $1$          |

The mapping above is the link between the Boolean math of old and the binary math we're interested in for building digital computers.

When working with Boolean logic statements, it'd be cumbersome to always have to write out the full statement! Instead, we usually pick a letter of the alphabet to act as a placeholder for the statement. For example, instead of writing down the full statement "it is raining," we may instead write just the letter $R$. (I chose "R" because it's the first letter of the key word in the statement, "it is $R$aining," but any other letter would work just as well.) These single-letter placeholders are called **variables**.

> If you've taken high school algebra, you might remember seeing a lot of variables in algebra too. Boolean variables are a lot like the variables you learned in algebra, with a key difference: in algebra, a variable can be used to represent any number, whereas in Boolean logic, a variable represents a Boolean value: either true or false ($1$ or $0$). Trying to mix algebraic variables and Boolean variables would be like mixing apples and oranges!

So, in summary, there are two Boolean values: "true," which can also be written as a binary $1$, and "false," which can be written as a binary $0$. In Boolean logic, we can work on Boolean values directly, or we can use variables (like $R$) to refer to statements (like "it is raining"), which can either be true or false.

Knowing that, let's see what we can do with Boolean values and variables.We're interested in three main Boolean operations: the *not* ("negation"), *and* ("conjunction") and *or* ("disjunction").

## Not (Negation)

The "not" operation (also known more formally as "negation") is the simplest of all Boolean operations: it's the only one that takes just one Boolean value or variable as input.

Negation produces the opposite of a given input value; that is, `not(true)` evaluates to `false`, and `not(false)` evaluates to `true`. When applied to logic statements, negation produces the opposite statement: if you negate the statement "it is raining," you get the opposite statement, "it is <ins>not</ins> raining." Similarly, if you started with the statement "it is not raining," then negating that would give you the opposite: "it <ins>is</ins> raining."

In mathematic notation, negation is represented using the $\neg$ ("not") symbol. So if $R$ represents the statement "it is raining," then $\neg R$ (pronounced "not R") represents the opposite statement: "it is <ins>not</ins> raining."

You may have noticed there is no $\neg$ key on your keyboard! That's why programmers represent negtation using a different symbol; `~` and `!` are both common choices. So if `R` represents the statement "it is raining," then `~R` or `!R` might be valid ways to represent the opposite statement: "it is <ins>not</ins> raining." (Both `~R` and `!R` are also pronounced "not R.")

## And (Conjunction)

The "and" operation (known formally as "conjunction") indicates whether two inputs values are both "true."

Growing up, you may have played a classic children's game to practice coordination, where you tried to use one hand to pat the top of your head, while at the same time using your other hand to rub your stomach. The goal of the game is to do both at the same time: it's not enough to do one or the other!

That's kind of how the "and" operation works. Consider two logical statements: "I am patting my head" and "I am rubbing my stomach." The pat head / rub stomach game requires a Boolean "and" of both of these statements: if both are true, then you're playing the game right &mdash; if either is false, you're doing it wrong!

In mathematic notation, conjunction is represented using the $\land$ ("and") symbol. So if $H$ is the statement "I am patting my head" and $S$ is the statement "I am rubbing my stomach," then $H \land S$ (pronounced "$H$ and $S$") tells you whether or not you're playing the game correctly. In other words, $H \land S$ is 'true' when both $H$ and $S$ are both true; however, if either $H$ or $S$ is 'false,' then $H \land S$ is also false.

Just like before though, there isn't a $\land$ symbol on your keyboard. So in computer code, we usually use the `&` symbol instead: so the expression `H & S` ("H and S") would tell you whether or not you're playing the pat head / rub  stomach game correctly.

## Or (Disjunction)

The "or" operation (formally "disjunction") indicates whether either or both of two input values are both "true."

Let's say you're a business, and you ship packages with expensive, fragile contents. You might then add a [tip indicator](https://www.google.com/search?client=safari&rls=en&q=tip+indicator&ie=UTF-8&oe=UTF-8) to the outside of the box so the shipper and the customer can see whether or not the box has been tilted or dropped in transit. This indicator should indicate if the box was tilted, dropped, or both.

That's what the Boolean-or operation does. Say $T$ is the statement "the box has been tilted" and $D$ is the statement "the box has been dropped." Then "$T$ or $D$" tells you whether the box was mishandled (tilted and/or dropped) during shipment. Note that "$T$ or $D$" should still be true if both $T$ and $D$ are true; that is, if the box was both tilted and dropped, we definitely want the tip indicator to have been set off! The Boolean-or operator would be pronounced "and/or" in everyday speech.

In mathematic notation, disjunction is represented using the $\lor$ ("or") symbol. The tip indicator from the example above should output $T \lor D$ , where $T$ means the box has been tipped and $D$ means the box has been dropped. Just like before, there isn't a $\lor$ symbol on your keyboard; computer code usually uses the vertical pipe symbol `|` instead. So, in code, `T | D` might tell you whehter the box has been tipped and/or dropped.

## Exclusive-Or

As mentioned above, the normal "or" (disjunction) operator doesn't discriminate between "either" or "both" &mdash; in other words, when both input values are 'true,' the Boolean-or of those values is also 'true.' Sometimes it's useful for "or" to mean "either," but not "both." For example, if you're a retailer accepting returned merchandise from customers, you might offer a refund or store credit, but certainly not both!

These are the semantics provided by the "exclusive-or" operation, which in computing circles is often shortened to "xor" (pronounced "ex-or"). In the example above, if $R$ means offering the customer a refund and $C$ means offering the customer store credit, then "$R$ xor $C$" is an acceptable way of processing the return &mdash; you allow either a refund or store credit, but not neither, and certainly not both!

Mathematically, we use the $\oplus$ symbol to denote the xor operation; so, for the example above, we'd write $R \oplus C$ to indicate how we'd process customer returns. In computer code, we often use the `^` symbol instead, and would equivalently write `R ^ C`.

## Truth Tables

Boolean operations are classically visualized using a tool called a "truth table," which is just a table that lists the output of the operation for each possible set of inputs (which, in turn, works because there are so few possible inputs!) The truth table below outlines the behavior of the not, and, or and xor operations defined above:

| $A$  | $B$  | $\lnot A$ | $A \land B$ | $A \lor B$ | $A \oplus B$ |
| ---- | ---- | --------- | ----------- | ---------- | ------------ |
| $0$  | $0$  | $1$       | $0$         | $0$        | $0$          |
| $0$  | $1$  | $1$       | $0$         | $1$        | $1$          |
| $1$  | $0$  | $0$       | $0$         | $1$        | $1$          |
| $1$  | $1$  | $0$       | $1$         | $1$        | $0$          |

As a reminder, the operators listed in the table above are as follows:

* $\lnot A$ ("not $A$") gives the opposite of $A$
* $A \land B$ ("$A$ and $B$") indicates whether $A$ and $B$ are both true
* $A \lor B$ ("$A$ or $B$") indicates whether $A$ and/or $B$ is true
* $A \oplus B$ ("$A$ xor $B$") indicates whether $A$ or $B$ is true, but not both

If you haven't done so already, take a minute to study the table above and make sure it makes sense! We're about to start working on multi-digit binary math, and doing so will build directly on the Boolean math we learned here.

## Preview: Logic Gates

You might be wondering: what does Boolean math have to do with computers?

Remember from the previous chapter that we decided to use switching to represent binary numbers in electrical circuitry &mdash; one switch per binary digit. We also decided to use networks of transistors (electrically-controlled switches) to implement math on binary numbers.

What we haven't talked about yet &mdash; and where Boolean math will come in handy &mdash; is how to design those transistor networks. Typically, the way you do this is to build one kind of transistor network, called a "logic gate," for each of the Boolean operations above (namely: not, and, or, xor). Then you figure out how to combine logic gates to implement the higher-level arithmetic operations you're interested in.

That's the thing we're going to talk about on the next page: how to combine single-digit Boolean operations to implement multi-digit binary arithmetic. Onward!











