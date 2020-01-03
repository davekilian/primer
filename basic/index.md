---
layout: chapter
title: A Basic Computer
---

It is incredible to behold how fast and complex computer hardware has become since we first started building computers in earnest back in the 1940s-1950s.  [The power adapter for a modern MacBook Pro laptop includes its own onboard computer that is more powerful than the earliest Macintosh computers](https://www.ibtimes.com/your-macbook-power-adapter-has-more-powerful-processor-original-mac-2202242). For several decades, computer hardware has been improving at an exponential rate, roughly doubling in complexity every two years &mdash; the industry has managed to hit this number so consistently for such a long time that the phenomenon was even given a name: [Moore's Law](https://en.wikipedia.org/wiki/Moore%27s_law).

In this chapter we will build ourselves a "minimum viable" computer. While this computer we will describe meets all reasonable definitions of the term "computer," and even resembles some of the first computers ever built, it will be a vast oversimplification of the computers we use today.

So let's get started!

## Computers and Calculators

At the heart of any computer is a programmable calculator. To understand what this means, let's take a look back at where the term computer came from:

"Computer" used to refer to a job description, not unlike "engineer" or "salesperson," rather than as a thing. Academic, scientific and engineering institutions employed (human) computers to crunch numbers for them. Computers would often employ calculators to aid them in their work (and since these were the days before digital calculators, they would often use mechanical calculators, notably a type of mechanical calculator called the  [slide rule](https://en.wikipedia.org/wiki/Slide_rule)). 

A reasonable question to ask is, why did we need computers when we already had perfectly functional calculators? What were the computers doing that calculators weren't?

The answer lies in the complexity of the computations: sometimes, the institution employing computers had a lot of data points, and needed people to crunch through all the data, running the same equations over and over on different input numbers to obtain some useful results. Other times, the institutions had very complex equations that required a lot of arithmetic to solve, requiring them to split the equation into smaller pieces, hand them out to individual computers, and combine their results at the end.

So, the main things computers were doing that their calculators couldn't was to string multiple calculations together: their slide rules might be able to add, subtract, multipy, divide, square or take the square root of numbers; but we needed computers to run sequences of related calculations.

### An Example

We're going to borrow an example from high school algebra &mdash; but we're just going to churn through arithmetic without needing to understand what the formulas mean, so don't worry if you've never taken algebra or you've forgotten most of it by now.

We're going to compute the solutions to quadratic equation using the quadratic formula. The solution to a quadratic equation with coefficients $A$, $B$ and $C$ is given by the following formula:

​	$\dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$	

So for example, the solution to $0 = 2x^2 + 5x + 3$ is:

​	$\dfrac{-5 \pm \sqrt{5^2 - 4 * 2 * 3}}{2(2)}$

Except there's a $\pm$ sneaking around in there, which is really a shortcut for saying there are two solutions given by two very similar-looking formulas, once which replaces $\pm$ with a $+$ and another which replaces $\pm$ with a $-$:

​	$\dfrac{-5 + \sqrt{5^2 - 4 * 2 * 3}}{2(2)}, \dfrac{-5 - \sqrt{5^2 - 4 * 2 * 3}}{2(2)}$

Say I asked you to compute these, and gave you a calculator that can do the following things:

* **punch in** a number
* **add** another number to the current number
* **subtract** another number from the current number
* **multiply** another number with the current number
* **divide** another number out of the current number
* **negate** the current number
* **square** the current number
* take the **square root** of the current number
* **clear** the current number

How would you break down these formulas and compute their solutions? There are actually lots of perfectly valid ways to do this, some better than others. We're going to list one of them below, but before moving on, take another look at the formulas above and think how you'd do this.

Done? Then here's our example:

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

Now let's say we had 1,000 different quadratic equations we wanted to solve, exactly like this. We don't want to have to think through how to punch the formula into the calculator every time, so instead we might want to distill the above down to just the steps we want to carry out:

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

What we just wrote here is a **program**. A program is just a sequence of steps; in a computer program, each of those steps is a calculation.

At the heart of every computer (the ones we use today, which replaced the human ones) is a programmable calculator designed to churn through programs much like this one. The job of a computer programmer is, when presented with a problem, to come up with a program which solves that problem, as a sequence of steps the computer's internal calculator supports. The computer then **executes** the program, churning through each step and doing exactly what each step says using the onboard calculator.

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or playing YouTube videos, but we'll get there. Everything you do on a computer is ultimately an extension of this programmable calculator, and over the course of this book, we'll build up to there.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

## A Basic Computer

For the rest of this chapter, let's look at how you build a computer that carries out programmed sequences of calculations, like the program we designed above. 

We're going to start by building ourselves a digital calculator that can perform simple operations, and then turn it into a full-fledged computer that can be programmed just like we did above. We'll close out the chapter by adding a few more components that most computers have, like random-access memory, disk storage and user peripherals.