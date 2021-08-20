---
layout: chapter
title: A Basic Computer
---

How do computers work? This might seem like an innocent question, but search online and you might be surprised by how many different ways people try to answer it!

In this chapter we're going to show you how computers work by sketching out the design of a rudimentary computer. What we'll end up with will look more like the computers they were building in the early- to mid-1900s than what we build today, but that's okay: that kind of computer serves as the core of our modern computers, and we'll have the rest of this book to cover what modern computers add to the mix. Our design won't be all too historically accurate &mdash; we're going to build toward the computers that exist today, rather than looking at old designs that didn't pan out.

Ready? Then let's get started!

## What is a Computer?

If we want to design our own computer, knowing what a computer even is seems like a good place to start!

Much ink has been put to paper trying to define what a computer is, and what computing is. Depending on how much of an affinity (or maybe patience) you have for philosophical pontification and papers with names like "A Fundamental Theory of ...," you may find these to either be fascinating or kind of useless; but either way, we don't have room in this book to define computation that way &mdash; yet we still need a basic working definition to start our design.

Here's a reasonable, mostly-correct definition that we can use for now:

<center><i>A computer is a programmable calculator.</i></center>

Doesn't mean all too much yet, eh? One thing that might help is to examine where we got the word "computer" in the first place:

## Computing in the Old Days

The word "computer" predates the electronic devices that we think of one someone says the word. Before there were electronic computers, the computers were people &mdash; "computer" was a job title!

Computers were most often employed by academic, scientific and engineering institutions; that is, the people who tend to have big numerical problems and need to crunch through a lot of calculations. If you're getting bored with this book and you'd rather watch a movie for a while (you'll come back though, right?), the 2016 film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures) portrays computers working for NASA in the early 1960s.

You might think being good at doing arithmetic in your head would be a necessity for working as a computer, back in the day before we had computing devices. Although many computers were indeed good at doing arithmetic in their heads, the main goal of the job was *accuracy*: if you're potentially stringing dozens or even hundreds of calculations together, it's important not to make a mistake part of the way through and throw everything off! Even the computers who were great at arithmetic kept calculators on their desks for harder calculations and checking their work. (This was before cheap consumer electronics, so they were probably using mechanical calculators like [slide rules](https://en.wikipedia.org/wiki/Slide_rule).)

So if a computer's job wasn't to be good at arithmetic, what exactly were they doing? It's easiest to see using an example:

## You are the Computer

For a few minutes, you're going to play the role of a computer, as we walk through an example of a (very small) chunk of work someone might hire you to do as a computer.

Our example will come from high school algebra, but it's okay if you haven't seen it before or forgot how it works &mdash; like with real computers (both human and electronic), your job is to carry out the steps of the calculation accurately, regardless of what they do or why they were set up that way. Ignorance is bliss, as they say.

In [algebra](https://en.wikipedia.org/wiki/Algebra) (the "fill-in-the-blanks" branch of mathematics), one of the first big things students learn to do is learn to solve [quadratic equations](https://en.wikipedia.org/wiki/Quadratic_equation) by employing the [quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula). If you have a quadratic equation of the form:

​	$0 = Ax^2+Bx+C$

... where $A$, $B$ and $C$ are all numbers you know, but $x$ is unknown (i.e. a blank you need to fill in), you can solve for $x$ (compute its value) by employing the quadratic formula:

​	$x = \dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$

For example, if you were presented with the following equation:

​	$0 = 2x^2 + 5x + 3$

... and were asked to solve for $x$ algebraically &mdash; that is, figure out what value of $x$ causes everything to the right side of the equals side to reduce to zero &mdash; you'd start by realizing this is a quadratic equation where the value of $A$ is $2$, $B$ is $5$ and $C$ is $3$. We can solve for $x$ using the quadratic formula, with the correct numbers substituted in for $A$, $B$ and $C$:

​	$x = \dfrac{-5 \pm \sqrt{5^2 - 4(2)(3)}}{2(2)}$

If you've taken higher-level math classes, this might look easy enough to calculate; if not, it might look a little strange, because we're using a lot of shorthand notation from higher-level math. Let's rewrite the exact same thing the way you might have learned in school:

​	$x = (-5 \pm \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

Oh wait, there's still a '$\pm$' sneaking around in there. What does that mean? It's a short way of telling us there are actually *two* quadratic formulas: one with $\pm$ replaced with $+$, and another with $\pm$ replaced with $-$. So, according to the quadratic formula, there are two values of $x$:

​	$(-5 + \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

​	$(-5 - \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

Notice the top line has a $+$ after the $-5$, and the other has $-$ instead.

Okay, my computer friend, time to get to work! Compute the value of $x$ for me please!

You can have a calculator to help you with your work. Actually, for the sake of accuracy, I ask you to please use the calculator instead of doing arithmetic in your head. Your calculator can do the following things:

* allow you to **punch in** digits of the 'current number'
* **add** another number to the current number
* **subtract** another number from the current number
* **multiply** another number with the current number
* **divide** another number out of the current number
* **negate** the current number
* **square** the current number
* take the **square root** of the current number
* **clear** the current number

I'll also give you some paper, so you can write down any partial calculations you're going to need later.

Alright, so, how are you going to compute the quadric formula using the tools I gave you?

There are plenty of good ways to break down the formulas into sequences of calculations. Try to come up with your own! Once you have your own complete sequence of steps, you can move on below where we've written ours:

> ### Computing the Quadratic Formula
>
> First we'll compute $-B$:
>
> | **Step**                               | **Calculator Value** |
> | -------------------------------------- | -------------------- |
> | **punch in** $B$, which is to say, $5$ | `5`                  |
> | **negate** the current value           | `-5`                 |
>
> On a piece of paper we'll write down the value of $-B$ as $-5$ (maybe we didn't *need* a calculator for that one ...). Next we'll compute $B^2$:
>
> | Step                           | **Calculator Value** |
> | ------------------------------ | -------------------- |
> | **clear** the calculator       | `0`                  |
> | **punch in** $B$, which is $5$ | `5`                  |
> | **square** it                  | `25`                 |
>
> We'll write down $B^2=25$ on our piece of paper. On to $4AC$:
>
> | Step                            | **Calculator Value** |
> | ------------------------------- | -------------------- |
> | **clear** the calculator        | `0`                  |
> | **punch in** $4$                | `4`                  |
> | **multiply** by $A$, which is 2 | `8`                  |
> | **multiply** by $C$, which is 3 | `24`                 |
>
> We'll write down $4AC=24$ on our piece of paper. Now we have enough to compute a bigger chunk of the formula: $\sqrt{B^2-4AC}$:
>
> | Step                                         | **Calculator Value** |
> | -------------------------------------------- | -------------------- |
> | **clear** the calculator                     | `0`                  |
> | **punch in** the value of $B^2$ which was 25 | `25`                 |
> | **subtract** the value of $4AC$ which was 24 | `1`                  |
> | take the **square root**                     | `1`                  |
>
> It turns out $\sqrt{^2-4AC} = 1$; let's write that down too. Now we'll take care of $2A$:
>
> | Step                          | **Calculator Value** |
> | ----------------------------- | -------------------- |
> | **clear** the calculator      | `0`                  |
> | **punch in** 2                | `2`                  |
> | **mutiply** by $A$ which is 2 | `4`                  |
>
> We'll write down $2A=4$ as well .This is what our piece of paper looks like now:
>
> > $-B=-5$
> >
> > $B^2=25$
> >
> > $4AC=24$
> >
> > $\sqrt{B^2-4AC}=1$
> >
> > $2A=4$
>
> All that's left to do now is put these values together to get the two solutions via the two formulas. We'll start with the $+$ side of the $\pm$:
>
> | Step                                            | **Calculator Value** |
> | ----------------------------------------------- | -------------------- |
> | **clear** the calculator                        | `0`                  |
> | **punch in** the value of $-B$, namely $-5$     | `-5`                 |
> | **add** the value of $\sqrt{B^2-4AC}$, namely 1 | `-4`                 |
> | **divide** by the value of $2A$ which is 4      | `-1`                 |
>
> And we get our first solution: $-1$. Repeating for the $-$ side of the $\pm$:
>
> | Step                                                 | **Calculator Value** |
> | ---------------------------------------------------- | -------------------- |
> | **clear** the calculator                             | `0`                  |
> | **punch in** the value of $-B$, namely $-5$          | `-5`                 |
> | **subtract** the value of $\sqrt{B^2-4AC}$, namely 1 | `-6`                 |
> | **divide** by the value of $2A$ which is 4           | `-1.5`               |
>
> And our second solution is $-1.5$. Ba-da-bing, ba-da-boom, we're done!

## From Computer to Programmer

Using this example, we now have a pretty good idea how to tackle any quadratic equation. All we need to do is extract the set of steps, and use placeholders $A$, $B$ and $C$ for the coefficients:

> 1. **take as input** three polynomial coefficients $A$, $B$ and $C$
> 2. **clear** the calculator
> 3. **punch in** $B$
> 4. **negate** it
> 5. **write down** the resulting value as $-B$
> 6. **clear** the calculator
> 7. **punch in** $B$
> 8. **square** it
> 9. **write down** the resulting value as $B^2$
> 10. **clear** the calculator
> 11. **punch in** 4
> 12. **multiply** by $A$
> 13. **multiply** by $C$
> 14. **write down** the resulting value as $4AC$
> 15. **clear** the calculator
> 16. **punch in** the previously computed value for $B^2$
> 17. **subtract** the previously computed value for $4AC$
> 18. take the **square root**
> 19. **write down** the resulting value as $\sqrt{B^2-4AC}$
> 20. **clear** the calculator
> 21. **punch in** 2
> 22. **multiply** by $A$
> 23. **write down** the resultinng value as $2A$
> 24. **clear** the calculator
> 25. **punch in** the previously computed value for $-B$
> 26. **add** the previously computed value for $\sqrt{B^2-4AC}$
> 27. **divide** by the previously computed value for $2A$
> 28. **output** the result as the first solution
> 29. **clear** the calculator
> 30. **punch in** the previously computed value for $-B$
> 31. **subtract** the previously computed value for $\sqrt{B^2-4AC}$
> 32. **divide** by the previously computed value for $2A$
> 33. **output** the result as the second solution

This thing is called a *program*.

If you look up the term "program" in a dictionary, it'll tell you a program is just a sequence; for example, if you go to a piano recital, someone might hand you a piece of paper entitled "program" giving you the scheduled sequence of performances for the recital. A computer program is also a sequence: a sequence of steps to carry out, where each step is a calculation.

This is why we're calling computers (the devices, not the people) *programmable* calculators. Every computer has a calculator inside of it somewhere, but you don't use that calculator directly; instead, you provide the computer with a program, which specifies a sequence of calculations the computer should perform. The computer then "executes" the program, by churning through each step one by one and doing whatever calculation the step says to do.

So, if you want to build a computer, you're going to need to build a calculator, as well as something that can feed in a sequence of calculations.

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or watching Netflix, but we'll get there in time. Everything you do on a computer is ultimately an extension of this programmable calculator, and we'll build our way up to these kinds of things over the course of this book.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

Let's start going about seeing how one builds a programmable calculator &mdash; we'll start by building ourselves a digital calculator, and then we'll turn it into a full-fledged computer which can execute programs using the calculator. We'll close out the chapter by introducing a few more components that are critical for writing programs in practice.