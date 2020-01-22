---
layout: chapter
title: A Basic Computer
---

In this chapter we're going to answer what seems like an easy question:

<center><i>How do computers work?</i></center>

This is a question near and dear to me &mdash; I once tried to find a good answer to this question online, and in failing to find a satisfying one, I ended up on the path that led me to become the professional software engineer I am today.

You may find it surprising that, for such a basic question, the field of computing hasn't agreed on a simple, widely taught answer to this question. Many professional software developers and hardware engineers alike would be hard-pressed to give you a clear answer (although each might be able to explain their own little piece of the puzzle in detail). I certainly had a lot of trouble finding a good answer back when I was trying to answer this question myself.

That's why, in this chapter, we're going to nail down the answer by building ourselves a 'minimum viable' computer!

## Computers and Calculators

If we're going to build a computer and see how they work, the very first thing we need is a definition of what a computer is. To avoid philosophical pitfalls, we'll stick to a practical, no-frills working definition: a computer as a "programmable calculator."

To make a bit more sense of that, let's take a look back at where the term originally came from:

"Computer" used to refer to a job description, not unlike "engineer" or "salesperson," rather than as a device or thing. Academic, scientific and engineering institutions employed (human) computers to crunch numbers for them. Computers would often employ calculators to aid them in their work (and since these were the days before digital calculators, they would often use mechanical calculators, notably a type of mechanical calculator called the  [slide rule](https://en.wikipedia.org/wiki/Slide_rule)). 

A reasonable question to ask is, why did we need computers when we already had perfectly functional calculators? What were the computers doing that calculators weren't?

The answer lies in the complexity of the computations: sometimes, the institution employing computers had a lot of data points, and needed people to crunch through all the data, running the same equations over and over on different input numbers to obtain some useful results. Other times, the institutions had very complex equations and formulas that required a lot of arithmetic, requiring them to split the equation into smaller pieces, hand them out to individual computers, and combine their results at the end.

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

Say we gave 1,000 different sets of quadratic equation coefficients to a (human) computer, and asked for the solutions to all 1,0000 of them. After thinking through the first few sets, our friend the computer will probably start to remember the steps needed by heart, allowing him or her to churn through sets quickly.

If you asked the computer how to compute these formulas, he or she would probably be able to conjure up something like this:

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

If this looks familiar, it's because we got by starting with the example formula we computed earlier, and just pulling out the 'steps' from the tables.

This list, by the way, is called a **program**. The term "program" in general refers to any old sequence (if you go to a piano recital, someone might hand you a 'program' telling you who's going to play what, and in what order). A computer program is a sequence where each step is a calculation.

This is where we get our working model of a computer as a programmable calculator: our (mechanical, no longer human) computer will be a device that, given a program, can **execute** it, churning through each step one by one and doing whatever calculation that step says. To make this work, at the heart of every computer you will find a calculator and some way to feed a program into the calcaultor.

The job of a computer programmer, when presented with a problem, is to come up with a program that solves that problem, as a sequence of steps the computer's internal calculator supports. When we figured out above how to compute the quadratic formula on our pretend calculator, that was programming!

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or playing YouTube videos, but we'll get there. Everything you do on a computer is ultimately an extension of this programmable calculator, and we'll build our way up to these kinds of things over the course of this book.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

## Building Our Computer

For the rest of this chapter, let's look at how you build a computer that carries out programmed sequences of calculations, like the program we designed above. 

We're going to start by building ourselves a digital calculator that can perform simple operations. Once we have a working calculator, we'll turn it into a full-fledged computer that can be programmed. We'll close out the chapter by adding a few more components that are critical to modern computers.