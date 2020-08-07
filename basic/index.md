---
layout: chapter
title: A Basic Computer
---

In this chapter, we're going to design ourselves a simple computer &mdash; the primitive kind that were once designed and built single-handedly.

The best way to start is to remind ourselves: what is a computer, anyways?

There are plenty of ways to tackle that question; many are too philosophical or math-y for this book. As a practical approximatation, let's say computers are *programmable calculators*.

To better understand what that means, it's helpful to look at where the term "computer" comes from. Once upon a time, "computer" was a job description. Academic, scientific and engineering institutions employed (human) computers to crunch numbers for them. The 2016 film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures) gives you an idea of who these computers were and what it was like to be one.

Many computers were drawn to the work because of they were good at arithmetic; nonetheless, computers frequently used calculators to aid them in their work (usually a [slide rule](https://en.wikipedia.org/wiki/Slide_rule)). The value in a computer wasn't necessarily to carry out arithmetic themselves so much as as to (correctly) string calculations together (usually lots of them) without making mistakes. Computers were typically brought in for very complex calculations involving many steps, or for large datasets requiring performing the same rudimentary calculations over and over.

Let's look at a simple example of the kind of work you might ask a computer to do for you. We're going to borrow an example from high school algebra &mdash; but we're just going to churn through arithmetic without needing to understand what the formulas mean, so don't worry if you've never taken algebra or you've forgotten most of it by now.

So, let's compute solutions to quadratic equation using the quadratic formula. The quadratic formula algebraically solves for $x$ in the following equation, where $A$, $B$ and $C$ are coefficients (any number, but a fixed one we already know ahead of time):

​	$0 = Ax^2 + Bx + C$

The solution to this equation is given by the quadratic formula:

​	$x = \dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$	

So for example, the solution to $0 = 2x^2 + 5x + 3$ is:

​	$x = \dfrac{-5 \pm \sqrt{5^2 - 4 * 2 * 3}}{2(2)}$

Except that's not quite the full story &mdash; there's a $\pm$ sneaking around in there, which is a shortcut for saying there are two solutions given by two very similar-looking formulas: once which replaces $\pm$ with a $+$ and another which replaces $\pm$ with a $-$. So the two solutions are:

​	$x = \dfrac{-5 + \sqrt{5^2 - 4 * 2 * 3}}{2(2)}$, or $x = \dfrac{-5 - \sqrt{5^2 - 4 * 2 * 3}}{2(2)}$

Say I asked you to compute these, and gave you a plain old calculator that can only do the following things:

* **punch in** a number
* **add** another number to the current number
* **subtract** another number from the current number
* **multiply** another number with the current number
* **divide** another number out of the current number
* **negate** the current number
* **square** the current number
* take the **square root** of the current number
* **clear** the current number

How would you break down these formulas and compute their solutions? Can you write down the sequence of steps you'd need to perform using your calculator to get a solution?

There are actually lots of perfectly valid ways to do this, some better than others. We're going to list one of them below, but before moving on, take another look at the formulas above and what functions the calculator gives you, and think how you'd do this.

Done? Then here's our solution:

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
> It turns out $\sqrt{^2-4AC} = 1$; let's write that down too. All that's left to take care of now is $2A$:
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

In computation, we would call this list of steps a **program**. If you look up the term "program" in a dictionary, it'll tell you a program is a sequence; for example, if you go to a piano recital, someone might hand you a piece of paper called a "program," telling you who's going to play what, in what order. A computer program is also a sequence: a sequence of steps, where each step is a calculation.

This is why we're calling computers (the devices, not the people) *programmable* calculators. Every computer has a calculator inside of it somewhere, but you don't use that calculator directly; instead, you provide the computer with a program, which specifies a sequence of calculations the computer should perform. The computer then **executes** the program, by churning through each step one by one, doing whatever calculation each step says. 

So to build a computer, you're fundamentally going to end up building a calculator and something that uses the calculator to execute a program (which is simply a sequence of calculations).

The job of a computer programmer is, when presented with a problem, to come up with a program that solves that problem, as a sequence of steps the computer's internal calculator can do. When we figured out above how to compute the quadratic formula on our pretend calculator, that was programming!

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or watching Netflix, but we'll get there in time. Everything you do on a computer is ultimately an extension of this programmable calculator, and we'll build our way up to these kinds of things over the course of this book.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

Let's start going about seeing how one builds a programmable calculator &mdash; in this chapter, we'll start by building ourselves a digital calculator, and then we'll turn it into a full-fledged computer processor (CPU) which can execute programs. We'll close out the chapter by introducing a few more components that are critical for writing practical programs.