---
layout: chapter
title: What is a Computer?
---

If we want to know how computers work, it would sure be handy to know what a computer is! Much ink has been put to paper trying to nail down exactly what a computer is &mdash; and isn't &mdash; but much of that borders too much on math or philosophy to be helpful in this book. For now, let's just say this:

<center><i>A computer is a programmable calculator.</i></center>

To understand what this means, it might help is to see where we got the word "computer" from:

## Computing in the Olden Days

Nowadays everybody knows a computer is an electronic device, usually with some kind of screen. But the word "computer" was already around long before we had these devices &mdash; the original computers were people, and "computer" was a job! Computers were brought in to crunch through big numerical problems, most often by academic, scientific and engineering instutations. The 2016 film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures) portrays computers working for NASA in the 1960s.

You might think that computers needed to be good at arithmetic &mdash; they often were! &mdash; but calculator use was still pretty common. That's because, ultimately, the job of a computer was to perform sequences of calculations *accurately*: you wouldn't want one little mistake throwing off the whole result!

To better understand what computers did and why, let's do an example! In algebra, a quadratic equation is defined by three numbers, which we'll name $A$, $B$ and $C$. To solve a quadratic equation, you plug those numbers into the quadratic formula:

​	$\dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$

So, for example, if I gave you the values $A=2$, $B=5$ and $C=3$ and asked you to solve, you would plug those values into the quadratic formula by substituting the assigned values for $A$, $B$ and $C$, like this:

​	$\dfrac{-5 \pm \sqrt{5^2 - 4(2)(3)}}{2(2)}$

If you've taken higher-level math classes, this might look easy enough to calculate; if not, it might look a little strange, because we're using a lot of shorthand notation from higher-level math. Let's rewrite the exact same thing the way you might have learned in school:

​	$(-5 \pm \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

Ah, but there's still a '$\pm$' sneaking around in there. That thing is shorthand telling us there are actually *two* quadratic formulas: one with $\pm$ replaced with $+$, and another with $\pm$ replaced with $-$. So we actually need to do two different, but very similar sets of calculations:

​	$(-5 + \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

​	$(-5 - \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

Notice the top line has a $+$ after the $-5$, and the other has $-$ instead.

We're going to want to calculate these two formulas.

For starters, let's use a calculator to help us with our work. Even when we could do the arithmetic in our heads, we'll use this calculator anyways so we can be extra certain we haven't made any mistakes. After all, being a computer is about being accurate more than being clever!

Say our imaginary calculator can do the following things:

* allow you to **punch in** digits of the 'current number'
* **add** another number to the current number
* **subtract** another number from the current number
* **multiply** another number with the current number
* **divide** another number out of the current number
* **negate** the current number
* **square** the current number
* take the **square root** of the current number
* **clear** the current number

We'll also use some paper, so we can write down any partial calculations for later.

So, given these tools, how would you compute the quadratic formula for the $A$, $B$ and $C$ values I gave you? There are plenty of good ways to break down the formulas into sequences of calculations. Try to come up with your own! Once you have your own complete sequence of steps, take a look at ours below:

> ### Computing the Quadratic Formula
>
> First we'll compute $-B$:
>
> | **Step**                               | **Calculator Value** |
> | -------------------------------------- | -------------------- |
> | **punch in** $B$, which is to say, $5$ | `5`                  |
> | **negate** the current value           | `-5`                 |
>
> On a piece of paper we'll write down the value of $-B$ as $-5$. Next we'll compute $B^2$:
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
> It turns out $\sqrt{B^2-4AC} = 1$! Let's write that down too. Now we'll take care of $2A$:
>
> | Step                           | **Calculator Value** |
> | ------------------------------ | -------------------- |
> | **clear** the calculator       | `0`                  |
> | **punch in** 2                 | `2`                  |
> | **mutiply** by $A$, which is 2 | `4`                  |
>
> We'll write down $2A=4$ as well. This is what our piece of paper says now:
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

Using this example, we now have a pretty good idea how to tackle any quadratic equation. All we need to do is extract the set of steps, and put the placeholders $A$, $B$ and $C$ back in to replace $2$, $5$ and $3$:

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

This thing is called a *program*. If you've never written a program before, well, congratulations on writing your first program!

## Programs and Computers

In the example above, we acted as both the programmer and the computer: we were programming when we decided what sequence of steps would give us the answer we needed, and we were computing when we carried those steps out by hand.

If you look up the term "program" in a dictionary, it'll tell you a program is a sequence; for example, if you go to a piano recital, someone might hand you a "program" printed on paper telling you the sequence of performances scheduled for the recital. A computer program is also a sequence: a sequence of steps to carry out, where each step is a calculation.

This is why we're calling computers *programmable* calculators. Every computer has a calculator inside of it somewhere, but you don't use that calculator directly; instead, you provide the computer with a program consisting of a sequence of calculations the computer should carry out. The computer then "executes" the program, going through each step of the program and carrying it out using the internal calculator.

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or watching Netflix, but we'll get there in time! Everything you do on a computer is ultimately an extension of this programmable calculator, and we'll build our way up to these kinds of things over the course of this book.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

Next up: let's see *how* one designs one of these programmable calculators.