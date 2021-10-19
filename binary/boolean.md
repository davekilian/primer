---
layout: chapter
title: Binary&#58; Boolean Math
---

A single binary digit has two possible values, $0$ and $1$. Compared to the math you grew up with, a single binary digit might not seem like much to work with, but it turns out you can do some pretty interesting math with just $0$ and $1$. On this page, we're going to learn a little about that.

Whenever we need to do math on a single-digit binary number in a computer, we **Boolean** logic, a mathematical framework named after its inventor, George Boole. Boole published his framework in the mid-1800s, about a hundred years or so before the first electronic computers. What was Boole doing with binary numbers a hundred years before we needed them for computers?

Well, Boole wasn't studying computers. He was studying logic!

## Logic

Logic is a way of extending your knowledge about the world, without having to go out and observe the new facts. Although thinking about logic is abstract and tricky, using logic is easy &mdash; you do it any time you make an assumption!

For example, imagine you had a teacher who, as a rule, would always bring in an umbrella when there was rain in the forecast, but never on days when the forecast was dry. Today, your teacher brought in am umbrella. What does that tell you? Why, there must be rain in the forecast, of course!

See what happened there? You extended your knowledge about the world ("there must be rain in the forecast today") without needing to make your own observation (checking the forecast yourself). That's logic!

Now, a lot of people have been studying who logic works for a long time, and they managed to come up with some pretty big words to describe it! You don't need to know them in depth to understand computers, but we'll talk about it anyways because it provides a useful backdrop for thinking about Boolean logic. (If you get bored, feel free to jump ahead to the next heading.)

Alright, ready? Here's formal logic in a nutshell:

When you use logic, you always start with a set of **premises**. Each premise is a fact about the world. You accept all premises as true for the sake of argument: maybe you really believe the premises, or maybe you're playing "what if?" and want to see what would happen if the premises were true. 

In the umbrella example, we had three premises:

* Your teacher brings in an umbrella when rain is in the forecast
* Your teacher does not bring in an umbrella when there is no rain in the forecast
* Your teacher brought in an umbrella today

From our premises, we want to derive a **conclusion**: a new, non-obvious fact based on the premises. We should be able to determine the conclusion is true by just using the premises; we should not have to go out and observe the conclusion directly. (Although checking we were right isn't necessarily a bad idea!)

In the umbrella example, the conclusion was:

* There is rain in the forecast today

How do we link premises to a conclusion? Usually we use a process called **deductive reasoning**. The idea is to take all possible conclusions that relate to the premises, and eliminate the ones that don't fit with the premises. (The elimination part is where the "deductive" part of "deductive reasoning" comes from.) If, after this process of elimination, you end up with only one possible conclusion, then you know it must be true. To put it simply, there is just no other way things could be.

In the umbrella example, we might choose two possible conclusions: "there is rain in the forecast today" or "the is <ins>no</ins> rain in the forecast today." How do we know the first conclusion is correct? Well, we know the second conclusion cannot coexist with all the premises:

* Premise: Your teacher does not bring in an umbrella when there is no rain in the forecast
* Premise: Your teacher brought in an umbrella today
* Conclusion (incorrect): There is <ins>no</ins> rain in the forecast today

Since the premises are already accepted as true, and we can't make the conclusion and the premises fit together, the conclusion must be wrong. We eliminate it as a possibility. The only remaining possibility ("there is rain in the forecast today") *does* fit with all the premises. It must be true!

When only one possible conclusion fits a set of premises, we say the premises **imply** the conclusion. In our example, the premises imply the conclusion that "there is rain in the forecast today."

Together, a set of premises the conclusion they imply is called a **logical argument**. The umbrella example is, in fact, a logical argument!

Bored yet? Let's get back to Boolean math.

## Mathematical Logic

Now we know more or less what Boole knew about logic when he invented Boolean logic. So what was he doing?

The formal structure of logic we just learned originally came from philosophy. Philosophy is traditionally done using text: you write down an explanation of your thinking maybe in a book or an essay. There are some problems with this! First of all, writing can be ambiguous &mdash; even more so if you need to translate a text into a different language. Also, if you're spelling out an argument in text, then the argument has to fit entirely in our heads: we can't do this effectively for big, complicated arguments with lots of premises. Plus, wouldn't it be kind of cool to figure out a mathematical way of representing the exact same logical arguments?

Boole certainly seems to have thought so! He invented a mathematical notation system for representing and manipulating logical arguments. In theory, this system should be much less ambiguous than writing, and may even make it easier to work with big, complex logical arguments! Today, we would call Boole's notation system **Boolean logic**. Although it's named in honor of its pioneer, a lot of other people have worked on Boolean logic along the way!

In the end, Boolean logic didn't end up being all that useful as a tool. You probably never learned it in math class. However, Boolean logic did go on to play a role in the origin of some modern theoretical mathematics, including abstract algebra and group theory. Almost a hundred years later after Boole's initial publication, an electrical engineering grad student named Claude Shannon realized you could use Boolean logic in switching circuits to run computations on binary numbers, kicking off the modern computing revolution.

And that's why, nigh on 200 years later, you're about to learn a little about Boolean logic today!

## Boolean Logic

After its first introduction, Boolean logic has been improved and refined over the years to better fit the needs of modern mathematics. We're going to study modern Boolean logic, with a focus on the things we're going to need to start designing computer circuitry.

Boolean logic represents the relationships between logic statements. A **logic statement** is any sentence that can appear in a logical argument, either as a premise or the conclusion. Examples of logic statements include things like "my teacher brought in an umbrella today" (a premise) or "there is rain in the forecast today" (a conclusion).

In Boolean logic, every statement must either be true or false. To keep the system simple, there is no room for half truths or partical correctness! "True" and "false" are called **Boolean values**. All Boolean math operates on just these two Boolean values.

When we write down a Boolean value, we have two options: we can use the words "true" and "false," or we can use the numbers $1$ and $0$, where $1$ means "true" and $0$ means "false." (This, by the way, will end up being the link between Boolean math, binary math and switching circuits later on in the book.)

| Boolean Value | Binary Value |
| ------------- | ------------ |
| `false`       | $0$          |
| `true`        | $1$          |

When we're working on true/false Boolean logic statements, we usually don't bother writing down the full statement all the time. That would get cumbersome! Instead, we usually pick a letter of the alphabet to act as a placeholder for the statement. For example, instead of writing down the full statement "It is raining," we may instead write just the letter $R$  any time we want to refer to the full statement. (I chose "R" because it's the first letter of the key word in the statement, "it is $R$aining.") These single-letter placeholders are called **variables**.

> If you've taken an algebra class, you might remember algebra also uses a lot of variables. Boolean variables are a lot like the variables you learned in algebra, with a key difference: in algebra, a variable can be used to represent any number, whereas in Boolean logic, a variable represents a Boolean value: either true or false ($1$ or $0$). Trying to mix algebraic variables and Boolean variables would be like mixing apples and oranges.

So, in summary, there are two Boolean values: "true," which can also be written as a binary $1$, and "false," which can be written as a binary $0$. In Boolean logic, we can work on Boolean values directly, or we can use variables (like $R$) to refer to statements (like "it is raining"), which can either be true or false.

What can we do with Boolean values and variables? Let's take a look at the three main Boolean operations: the *not* ("negation"), *and* ("conjunction") and *or* ("disjunction") operations.

## Not (Negation)

The "not" operation (also known more formally as "negation") is the simplest of all Boolean operations: it's the only one that takes just one Boolean value or variable as input.

Negation produces the opposite of a given input value; that is, `not(true)` evaluates to `false`, and `not(false)` evaluates to `true`. When applied to logic statements, negation produces the opposite statement: if you negate the statement "it is raining," you get the opposite statement, "it is <ins>not</ins> raining."

In mathematic notation, negation is represented using the $\neg$ ("not") symbol. So if $R$ represents the statement "it is raining," then $\neg R$ (pronounced "not R") represents the opposite statement: "it is <ins>not</ins> raining."

You may have noticed there is no $\neg$ key on your keyboard! That's why, in computer code, negation is instead represented using a different symbol: `~` and `!` are common choices. So if `R` represents the statement "it is raining," then `~R` or `!R` might be valid ways to represent the opposite statement: "it is <ins>not</ins> raining." (Both `~R` and `!R` are also pronounced "not R.")

## And (Conjunction)

The "and" operation (known formally as "conjunction") indicates whether two inputs values are "true."

Growing up, you may have played a classic children's game to practice coordination, where you tried to use one hand to pat the top of your head, while at the same time using your other hand to rub your tummy. The goal of the game is to do both at the same time: it's not enough to do one or the other!

That's kind of how the "and" operation works. Consider two logical statements: "I am patting my head" and "I am rubbing my tummy." The pat head / rub tummy game requires a Boolean "and" of both of these statements: if both are true, then you're playing the game right &mdash; if either is false, you're doing it wrong!

In mathematic notation, conjunction is represented using the $\and$ ("and") symbol. So if $H$ is the statement "I am patting my head" and $T$ is the statement "I am rubbing my tummy," then $H \and T$ (pronounced "$H$ and $T$") tells you whether or not you're playing the game correctly.

Just like before though, there isn't a $\and$ symbol on your keyboard. So in computer code, we usually use the `&` symbol instead: so the expression `H & T` ("H and T") would tell you whether or not you're playing the pat head / rub tummy game correctly.

## Or (Disjunction)

> Follow the template for "and"
>
> Example: Email your teacher the assignment, or hand it in on paper. It's okay to do both, the teacher will just pick one. I feel like we should be able to do better though &mdash; something where two routes to doing something really do yeild a single shared result, not two identical results.

## Exclusive-Or

> Follow the template for "and". The name for the symbol in tex is oplus $\oplus$
>
> Example: I came in through the door \xor I came in through the window.

## Truth Tables

> Explain what a truth table is and show one for all the operations we outlined above. Use an empty hyphen for the 'second' input value for the not operator

## Compund Statements

> The 'meat' of Boole's framework comes from *combining* these operations.
>
> Some of the operations above can be decomposed into compound statements of lower-order operations. Do xor, implies, equivalent.
>
> Possible to rewrite a compound statement as a different, equivalent compound statement. This is the basis of Boolean algebra. (Is it? Confirm pls)
>
> Example: De Morgan's law is a classic.

## Other Boolean Operations

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

## Preview: Logic Gates

> Remind about the link between booleans and a single bit.
>
> Explain how on the next page, we'll show how we take these basic operations and use them to build 
>
> Then preview how we will build transistor networks for each boolean operation, and wire them together to implement binary math in circuitry
