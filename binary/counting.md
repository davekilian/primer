---
layout: chapter
title: Binary&#58; Counting
---

Binary can look pretty weird for sure, but it shares a lot in common with the 'normal' numbering you and I learned in school. So let's think for a bit ...

## ... How Do Numbers Work, Again?

If you can remember anything about your very first math class in school, it probably involved counting and writing down numbers.

There are lots of ways to write down numbers. For example, "$7$" in our regular system could also be written as $VII$ in Roman numerals, but both mean the same thing. The way we write down numbers is called a *numeral system*. The job of a numeral system is a lot like the job of a language: just like you can write the same word in many different languages, so can you write the same number in many different numeral systems. And yet, to think of a word you have to have some language &mdash; and to think of a number, you have to have a numeral system. I guess human brains are just weird that way.

The numeral system that you were taught in school is a form of [Arabic numerals](https://en.wikipedia.org/wiki/Hindu–Arabic_numeral_system). This system has its roots in the ancient [Brahmi](https://en.wikipedia.org/wiki/Brahmi_numerals) writing system, but wasn't fully completed until the 800s. Starting from where it originated, in the South Asian subcontinent, it then spread outward in every direction, evolving as it went. Eventually it marched all way the west across northern Africa, then up into Europe through Arabic-speakers in Spain. We call it "Arabic" numerals because of the way this numeral system made it into Europe, even though the system actually originated much further east!

We all know how this sytem works. We have 10 *digits*: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$ and $9$. The $0$ is special &mdash; we'll come back to it later &mdash; but the rest of the digits are just the first 9 numbers in our numeral system. What happens when we try to count past nine? Simple! We roll over to the next decimal place: so from $9$, we then go to $10$, $11$, $12$ and so on. Once we hit $19$, we go up to $20$, $21$, $22$ and so on. Only when we hit $99$ do we go to the next decimal place: $99$, $100$, $101$. Every knows this stuff. Too easy!

Have you ever thought about who they came up with this numeral system in the first place? For example, why did they decide to go with 10 digits?

## Digits

Here's a big hint: what can the word *digit* mean? In math, a digit is a number. In anatomy, a digit is a finger ... ah, of course! There are 10 digits because we have 10 fingers. You remember counting on your fingers, and that's certainly something people were in every society right before they started figuring out how to write down numbers.

What would our numeral system look like if we had a *different* number of fingers?

Imagine a world just like ours, wth the same history as ours, where they came up with the same Arabic numeral systems as us, except for one key difference: they have 2 fingers instead of 10. In that world, they'd probably end up with only two digits: $0$ and $1$, rather than our fuller $0$ through $9$.

How would counting look for those imaginary people?

Well, the first number would probably seem familiar: good old $1$.

But try to count past $1$ and, alas, we're already out of digits &mdash; mathematically and anatomically! So, of course, we move to the next number place: the number after $1$ is $10$.

But wait! &mdash; you might say &mdash; what about all the missing numbers? You can't just jump from $1$ to $10$! Well, it's tricky, but there actually *aren't* any missing numbers! Our two-fingered friends have all the same numbers we do; they're just labelling theirs differently. It's like they're speaking a similar, but slightly different numeric language than us &mdash; and their language means something different by $10$ than we do. (It's sort of like [false friends](https://en.wikipedia.org/wiki/False_friend), but for numbers instead of words.)

Think you might be getting it? Let's try to keep counting. What are the next few numbers, as our two-fingered friends would write them? The answer is below, so get out a sheet of paper now and try to write down the next few numbers *before* you move on and see what the right answer.

Ready? Okay, here's the answer: $1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"), $101$ ("five"), $110$ ("six"), $111$ ("seven"), $1000$ ("eight"), $1001$ ("nine"), $1010$ ("ten"). Did you get it right?

If you read the previous chapter carefully, you might already see where this is going. This is binary numbering! If you got the example above correct, you're ready to move on. If not, here's a quick table to help you see how binary numbers map to the way we write numbers:

| How you'd say it out loud | How you'd write it normally | How you'd write it in binary |
| ------------------------- | --------------------------- | ---------------------------- |
| one                       | 1                           | 1                            |
| two                       | 2                           | 10                           |
| three                     | 3                           | 11                           |
| four                      | 4                           | 100                          |
| five                      | 5                           | 101                          |
| six                       | 6                           | 110                          |
| seven                     | 7                           | 111                          |
| eight                     | 8                           | 1000                         |
| nine                      | 9                           | 1001                         |
| ten                       | 10                          | 1010                         |
| eleven                    | 11                          | 1011                         |
| twleve                    | 12                          | 1100                         |
| thirteen                  | 13                          | 1101                         |
| fourteen                  | 14                          | 1110                         |
| fifteen                   | 15                          | 1111                         |
| sixteen                   | 16                          | 10000                        |

Take a moment to study the table. If you understand how to count down each column, then congratulations: you already have a good handle on binary numbering!

## Numeric Bases

We just saw how our numeral system (Arabic numerals) is somewhat flexible on the number of digits you decide to use. If you use 10 digits, you get the system we all learned ins chool. If you use 2 digits, you get binary.

The number of digits one of these systems uses is called the numeral system's **basis**, or sometimes its "**radix**." The basis (radix) of our system is 10, so we call it "base 10." When we write in binary, we use the same Arabic numeral system, but we use a basis (radix) of 2. So we call binary "base 2."

> Do you find the term "base 10" confusing? If not, maybe you should! How can we rightfully call our numeral system "base 10" if the whole problem is disagreement over what "10" means? Wouldn't our imaginary two-fingered friends from the previous example *also* call their system "base 10"?
>
> The truth is, yup, they probably would. That's why, when we talk about a system's basis, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in school, and not "10" as our imaginary friends would mean it.

You can count using Arabic numerals in any basis. For example, here are a few of the smallest possible bases:

| Name       | Basis  | Digits                            |
| ---------- | ------ | --------------------------------- |
| Binary     | Base-2 | $0$, $1$                          |
| Trinary    | Base-3 | $0$, $1$, $2$                     |
| Quaternary | Base-4 | $0$, $1$, $2$, $3$                |
| Quinary    | Base-5 | $0$, $1$, $2$, $3$, $4$           |
| Senary     | Base-6 | $0$, $1$, $2$, $3$, $4$, $5$      |
| Septenary  | Base-7 | $0$, $1$, $2$, $3$, $4$, $5$, $6$ |

Did you notice there's no unary/base-1 in the table above? That's because binary is the smallest basis that works in our notation system: you need to have at least two digits to write "$10$," which is something that a system based on number places fundamentally relies on.

We also could have kept going. In fact, you can even use a basis higher than 10! For example, as we'll see later in the book, it's sometimes useful in computing to represent numbers in base-16, which is called **hexadecimal**. When we count in hexadecimal, we need more than 10 digits, so after $9$ we start borrowing letters from the alphabet: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$, $9$, $A$, $B$, $C$, $D$, $E$, $F$, $10$, $11$, ..., $19$, $1A$, $1B$, ..., $1F$, $20$ ,$21$.

## Why are we doing this again?

Hopefully now you have a pretty good idea about how changes of basis work, and how to count in binary. But we're starting to get into the weeds. Why were doing all this again? Why did we care about binary?

Remember from first chapter that we're going to build a computer out of electricial circuitry using the concept of *switching*. A switch has two possible states: on or off. Binary is a numbering system with two possible digits: $0$ or $1$. Because of this, we're going to be able to come back later and represent binary numbers in circuitry using switches, by using one switch per digit of a binary number.

Sound familiar? That's great!

Remember that the goal is to build a computer &mdash; a programmable calculator &mdash; using switch-based circuits that do math on binary numbers. Clearly, then, it'd be useful to think a little about how to do math on binary numbers! That's exactly what we'll do on the next page.