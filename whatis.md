---
layout: chapter
title: What is a Computer?
---

If we want to know how computers work, it would sure be handy to know what a computer is! Much ink has been put to paper trying to nail down exactly what a computer is &mdash; and isn't &mdash; but a lot of that borders too much on math or philosophy to be helpful in this book. For now, let's just say this:

<center><i>A computer is a programmable calculator.</i></center>

To understand what this means, it might help is to see where we got the word "computer" from:

## Computing in the Olden Days

When you talk about computers today, we think of electronic devices, touchscreens, keyboards and more. But the word "computer" was already around long before these electronics &mdash; the original computers were people, and "computer" was a job! Human computers were brought in to crunch through big numerical problems, most often by academic, scientific and engineering organizations. For example, the 2016 film [Hidden Figures](https://en.wikipedia.org/wiki/Hidden_Figures) portrays computers working for NASA in the 1960s.

You might think that computers needed to be good at arithmetic &mdash; they often were! &mdash; but calculator use was still pretty common. That's because it was more important for computers to be accurate than fast. It was important to be able to string together many calculations without making any mistakes; after all, it'd be no good to get an answer slightly faster if it's the wrong answer!

To better understand the work of a computer, it might be helpful to do an example. In algebra, a "quadratic equation" is defined by three numbers, which we'll name $A$, $B$ and $C$. To solve a quadratic equation, you plug those numbers into the "quadratic formula," which looks like this:

​	$\dfrac{-B \pm \sqrt{B^2 - 4AC}}{2A}$

So, for example, if I gave you the values $A=2$, $B=5$ and $C=3$ and asked you to solve, you would substitute the numbers $2$, $5$ and $3$ in for $A$, $B$ and $C$ respectively, like this:

​	$\dfrac{-5 \pm \sqrt{5^2 - 4(2)(3)}}{2(2)}$

The way we wrote the formula above uses shorthand notation that you might not be familiar with &mdash; it normally doesn't get introduced until around the time you take algebra. We can write the same thing without shorthand, like this:

​	$(-5 \pm \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

This might look more doable, but there's still one tricky bit left: a '$\pm$' sneaking around in there. $\pm$ is pronounced "plus or minus," and tells us there are actually *two* quadratic formulas: one with $\pm$ replaced with $+$, and another with $\pm$ replaced with $-$. So we actually need to do two different, but very similar sets of calculations:

​	$(-5 + \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

​	$(-5 - \sqrt{5 \times 5 - 4 \times 2 \times 3}) \div (2 \times 2)$

Hopefully that makes sense now. Let's pretend to be computers and try to calculate this!

You might be able to do this in your head, but let's resist the temptation and instead use a calculator to help us. After all, it's more important for a computer to be accurate than clever! Our imaginary calculator will be able to do the following things:

* allow you to **punch in** a number digit by digit
* **add** another number to the current number
* **subtract** another number from the current number
* **multiply** another number with the current number
* **divide** another number out of the current number
* **negate** the current number
* **square** the current number
* take the **square root** of the current number
* **clear** the current number

Oh, you can also have some paper, to write down any partial results you want to use again later.

Given these tools, how would you compute the two formulas above? There are plenty of good ways to break down the formulas into sequences of steps on the calculator. Try to come up with your own! Once you have your own complete sequence of steps, you can take a look at our example solution below:

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

Using this example, we now have a pretty good idea how to tackle any quadratic equation. All we need to do is extract the set of steps, and put the placeholders $A$, $B$ and $C$ back in for $2$, $5$ and $3$:

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

This thing is called a *program*. If you've never programmed before, well, congratulations on writing your first program!

## Programs and Computers

In the example above, we acted as both the programmer and the computer: we were programming when we decided what sequence of steps would give us the answer we needed, and we were computing when we carried those steps out by hand.

If you look up the word "program" in a dictionary, you'll find that it's just another word for "sequence." For example, if you go to a piano recital, someone might hand you a "program" telling you the sequence of performances scheduled for the day. A computer program is also a sequence: a sequence of steps to carry out, where each step is a calculation.

That's why we're saying a computer is a *programmable* calculator. Every computer has a calculator inside of it somewhere, but you don't use that calculator directly; instead, you provide the computer with a program, where each step in the program is the next calculation to perform. The computer that "executes" the program, going through each step and doing the specified operation on the internal calculator. By stringing many calculations together, you can do some pretty interesting things!

It might be hard right now to see how this programmable calculator relates to everyday computing tasks like loading your Twitter feed or watching Netflix, but we'll get there in time! Everything you do on a computer is ultimately an extension of this programmable calculator, and we'll build our way up to these kinds of things over the course of this book.

For now, just think of a computer as a programmable calculator, and you'll be doing pretty well.

Next up: let's see *how* one designs one of these programmable calculators.