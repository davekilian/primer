---
layout: chapter
title: Binary&#58; Counting
---

Binary can look pretty weird for sure, but it shares a lot in common with the 'normal' numbering you and I learned in school. So let's think for a bit ...

## ... How Do Numbers Work, Anyways?

If you can remember anything about your very first math class in school, it probably involved counting and writing down numbers.

There are lots of ways to write down numbers. For example, "$7$" in our regular system could also be written as $VII$ in Roman numerals, but both mean the same thing. The way we write down numbers is called a *numeral system*. The job of a numeral system is a lot like the job of a language: just like you can write the same word in many different languages, so can you write the same number in many different numeral systems. And yet, to think of a word you have to have some language &mdash; and to think of a number, you have to have a numeral system. I guess human brains are just weird that way.

The numeral system that you were taught in school is a form of [Arabic numerals](https://en.wikipedia.org/wiki/Hindu–Arabic_numeral_system). This system has its roots in the ancient [Brahmi](https://en.wikipedia.org/wiki/Brahmi_numerals) writing system, but wasn't fully completed until the 800s. Starting from where it originated, in the South Asian subcontinent, it then spread outward in every direction, evolving as it went. Eventually it marched all way the west across northern Africa, then up into Europe through Arabic-speakers in Spain. We call it "Arabic" numerals because of the way this numeral system made it into Europe, even though the system actually originated much further east!

We all know how this sytem works. We have 10 *digits*: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$ and $9$. The $0$ is special &mdash; we'll come back to it later &mdash; but the rest of the digits are just the first 9 numbers in our numeral system. What happens when we try to count past nine? Simple! We roll over to the next decimal place: so from $9$, we then go to $10$, $11$, $12$ and so on. Once we hit $19$, we go up to $20$, $21$, $22$ and so on. Only when we hit $99$ do we go to the next decimal place: $99$, $100$, $101$. Every knows this stuff. Too easy!

Even so, there's value in getting even more explicit. Let's take a closer look at counting using Arabic numerals.

## An *Algorithm* for Counting

An **algorithm** is a process for solving a computational problem. The term originates from math: unless you got to proof-based math courses in college, most of the math you learned in school was algorithmic. For example, division might be a mathematical operation, but *long division* &mdash; the specific set of steps you take to divide a multi-digit number by another multi-digit number &mdash; is an algorithm.

More concretely, an algorithm is a sequence of steps you take when solving a problem. In that way, an algorithm is a lot like a computer program, and indeed, the study of algorithms is a major component of the field of computer science! This is a book about computers and we're talking about math, so let's talk about an algorithm that comes so naturally to you, you probably never even think about it: counting!

> Let's think about how you count in Arabic numerals
>
> 1-9 is easy.
>
> Now what? We move to the next *position*, or *decimal place*. We reset the 1s place to 0 and add 1 to the 10s place.
>
> 10-19. Now what?
>
> Oh yeah, once again, it's the same idea: reset the 1s place to 0 and add 1 to the 10s place.
>
> 20 ...
>
> Okay, so eventually we get to 99. Then what? 
>
> Well to begin, we reset the 1s place to 0 and add 1 to the 10s place ... except we can't do that, because the 10s place is already 9. So what do we do? Why, the same thing of course! Reset the 10s place to 0, and add 1 to the hundreds place. 99 100
>
> Okay, so let's think about how to do that *algorithmically*.
>
> Pseudocode

## Digits

> Why ten digits?
>
> Here's a big hint: what can digit mean? In math, it's a number ... in anatomy, it's a finger! Of course, we have 10 digits because we have 10 fingers.
>
> What would our numbering system look like if we had a *different* number of fingers?
>
> Imagine a world identical to ours, with a history identical to ours, except for one key difference: in this imaginary world, humans have 2 fingers instead of 10. In that world, what would their numbering system end up looking like?
>
> Like us, they chose to have as many digits as they have fingers. Unlike us, they only have two fingers. So they would only have come up with two digits: $0$ and $1$.
>
> How would these people count in that system?
>
> Well, the first number would seem familiar: $1$. But, alas, now we're already out of digits &mdash; both mathematically and anatomically! So of course, we move to the next position: reset the 1s place to 0, and add 1 to the tens place. $1$ ("one"), $10$ ("two")
>
> Okay, you might ask, but what about all the missing numbers? You can't just jump from $1$ to $10$! Well, it's tricky, but actually there are no missing numbers! Our tw-ofingered friends have all the same numbers we do; they're just labelling theirs differently. 
>
> It's like they're speaking a different numeric 'language' than us &mdash; one that means something different by "10" than we do. (It's sort of like [false friends](https://en.wikipedia.org/wiki/False_friend), but for numbers instead of words.)
>
> In case it helps, look at the following table. In this table, we're going to count, starting from 1, in both number systems at the same time. Every row in this table is the *same number*, just written differently.
>
> > Insert table from the old draft
>
> In summary, our two-fingered friends use the same numbering system we do, except they only have two digits ($0$ $1$) whereas we have 10 ($0$ $1$ $2$ $3$ $4$ $5$ $6$ $7$ $8$ $9$). We could always use their system to count, if we had a reason to, just as they could always use our system if *they* wanted to. The numbering system is the same either way; the only thing that differs is the number of digits being used.
>
> The number of digits between 0 and 10 is called the numbering system's **basis** or sometimes its **radix**. The basis (radix) of our system is 10, so we call it "base 10," whereas our imaginary friends' system has a basis (radix) of 2, so we call it "base 2."
>
> > By the way, if you find the term "base 10" terribly confusing, you're completely justified. How can we call our system "base 10" if the whole problem is defining what "10" means? Wouldn't our two-fingered friends also call *their* system "base 10?"
> >
> > The answer is yup, they probably would. That's why, when we talk about bases, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in school, and not "10" as our imaginary friends would mean it.
>
> Let's do a quick exercise: go ahead and try to count in base 2. Count the number of fingers on your real hand &mdash; in other words, count to 10 using base 2.
>
> All done? Here's the answer: $1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"), $101$ ("five"), $110$ ("six"), $111$ ("seven"), $1000$ ("eight"), $1001$ ("nine"), $1010$ ("ten"). Did you get it right?
>
> If so, congrats on learning binary! Because binary is just a big fancy word that means base 2 numbering!

---

> Okay, so now that we've talked about binary, I'm going to add this as a long, boxed section. It's optional. You can skip to the next page if you want. You already get binary; this is just going to add a bit more depth to the conversation. But we're also reaching the intersection between math, language and human cognition, which is where things get dicey fast. So don't feel obligated to get through all this.
>
> Then rip the system down to its studs. What's going on? How would you convert between systems?

## How Numbers *Really* Work

> New intro. Basically say let's rip Arabic numerals down the studs. It turns out the way we write numbers is based on much higher-level math: it involves tricky things like addition, multiplication, and the special number $0$ baked in. Numeral systems are the intersection between math and language, which really makes this a mind-bender to think about. Luckily, you don't *have* to understand all this to understand binary. So if you get bored or confused, feel free to skip this and move on.

---

... or is it all that easy? These rules are not arbitrary: they combine the concepts of additional, multiplication and the number $0$ in a clever way. Let's peel back the curtain!

## How Numbers *Really* Work

You see, any numeral system has to solve one key problem: there are infinitely many numbers, and people aren't that good at memorizing stuff. We can't make up words for every number the same way we can make up words for concepts in language: there are just too many numbers! So, instead, we have to find a way that lets us represent any number using just a few things we memorized &mdash; such as those 10 digits.

How does the Arabic numeral system do that? The key idea is the use of *decimal places*. Each place represents some number, and the digit we put in that place says how many of that place.

For example, think of the number $234$. This is actually shorthand for saying I have

* $2$ hundreds, plus
* $3$ tens, plus
* $4$ ones

In mathematical notation, we might instead say $234$ is shorthand for $2 \times 100 + 3 \times 10 + 4 \times 1$. Seems easy enough!

Now, where this gets confusing is numbers like $100$. This number says i have ...

* $1$ hundred plus
* $0$ tends plus
* $0$ ones

Mathematically, we might instead say $100$ is shorthand for $1 \times 100 + 0 \times 10 + 0 \times 1$. Wait, what? How does saying $100$ devolves to $1 \times 100$ offer any insight whatsoever?

Okay, so we found the tricky part of our numeral system. You see humans have been coming up with systems to write down numbers for a long time &mdash; in fact, pretty much every society that developed written language started by writing numbers, not words &mdash; but it took us until about 1,000 years ago to come up with *this* numeral system. Because *this* numeral system is clever!

The basic idea of our system system involves *decimal places*. Even if you didn't realize it, these are special numbers to which we have assigned names: one, ten, hundred, thousand, and so on. Now, there are infinitely many places, just as there are infinitely many numbers, so even though we give names to the common places, eventually we run out of names and have to use compounds. So for example, the next place after 'thousand' is 'ten-thousand,' then 'hundred-thousand.' Then, after 'million,' there's 'ten-million' and 'hundred-million.'

Then the basic idea of our system is to write every number as a **combination of the places**. This is where the digits come in: the digits are basic numbers that can be multiplied with the place numbers; in turn, the 'place' numbers are strategically picked at every point we run out of digits.

> Why did it take so long to come up with this system? The key is the number $0$.
>
> You see, when $0$ was first invented, many people didn't initially accept it as a number: a number defines a quantity, and zero defines the absence of a quantity! Even today, we still find that zero breaks our mathematics in unique ways; for example, you can't divide by zero.
>
> Zero is the key to a place-based numeral system, because sometimes you don't have any of a particular place. The number $203$ is two hundreds and three ones, but no (zero) tens. Not having invented zero is part of why it took so long for humanity to come up with something like the Arabic numeral system.

Let's look at numbers again in that light.

So once again, the first few numbers are $1$-$9$. But using our definition, we know the secret pattern: there's a "place" number called one, and each of these is a different number of "ones." So really, $7$ is short for $7 \times 'one'$. When we run out of digits for the ones, we use the next place number: ten. The next number is a single ten, plus no ones: $10$, or $1 \times 'ten' + 0 \times 'one'$.

> Contrast this with Roman numerals: it has no number places. 



> Some thoughts here
>
> * We need to define combination more formally like a linear combination
> * We need to explain more clearly that "ten" isn't exactly the same thing as "$10$"
>
> It might be better to start with the algorithm first, and introduce terms like digit and place in that context. Then we can rewrite this section as an optional 'ripping down to the studs' analysis of how our numeral system works &mdash; and clearly say this is optional, you can skip it if you get bored or it didn't make sense right away.
>
> Have a sentence like this: I'm being really careful to write "ten" and not "$10$" because, in this context, they mean slightly different things: "ten" is a number we're basing our system on, and "$10$" is a combination, of a single "ten" and no "ones." In the end, though, "ten" and "$10$" refer to the same number; the difference between the two only has to do with the way we *write* numbers.
>
> One more key insight is that the places are defined in terms of digits. Whenever we use up all our digits in all our existing places, the next number is the next place. So the places are
>
> $9 + 1$
>
> $99 + 1$
>
> $999 + 1$
>
> $...$



---



> Segue into conversinos, because we don't natively think in binary.
>
> Regardless of the basis used, our numbering system is a shorthand for a decomposition like this: $2345 = 2 \cross 1000 + 3 \cross 100 + 4 \cross 10 + 5 \cross 1$. The only thing that changes, when you change bases, are the definitions of $1000$, $100$, $10$ and $1$. In binary, those are all powers of $2$: $1$, $2$, $4$, $8$, $16$, $...$. Spend long enough with computers and you will accidentally memorize a lot of powers of 2!
>
> Binary, having only two digits, has a weird property: each place is either $0$ or $1$. That means you can never multiply a 'place' by more than 1. Each place is either included once in the sum, or it's not included at all. That somewhat simplifies the task of converting between binary and decimal.
>
> Then show diagrams where each binary 'place' is annotated with its decimal amount.
>
> Walk through both conversions using examples.



> Here's a factoid. Does it fit anywhere?
>
> Base-2 is a somewhat special basis mathematically, because it's the smallest basis that works with our numbering system. You couldn't have base-1; after all, then your only digit to work with would be $0$ and thus the only number you could represent is $0$.


