---
layout: chapter
title: Binary&#58; Counting
---

Binary can look pretty weird for sure, but it shares a lot in common with the 'normal' numbering you and I learned in school. So let's think for a bit ...

## ... How Do Numbers Work, Again?

If you can remember anything about your very first math class in school, it probably involved counting and writing down numbers.

There are lots of ways to write down numbers. For example, "$7$" in our regular system could also be written as $VII$ in Roman numerals, but both mean the same thing. The way we write down numbers is called a *numeral system*. The job of a numeral system is a lot like the job of a language: just like you can write the same word in many different languages, so can you write the same number in many different numeral systems. And yet, to think of a word you have to have some language &mdash; and to think of a number, you have to have a numeral system. I guess human brains are just weird that way.

The numeral system that you were taught in school is a form of [Arabic numerals](https://en.wikipedia.org/wiki/Hindu–Arabic_numeral_system). This system has its roots in the ancient [Brahmi](https://en.wikipedia.org/wiki/Brahmi_numerals) writing system, but wasn't fully completed until the 800s, when we invented the number zero. Starting from where it originated, in the South Asian subcontinent, it then spread outward in every direction, evolving as it went. Eventually it marched all way the west across northern Africa, then up into Europe through Spain. We call the system "Arabic" numerals because it was brought into Europe by Arabic-speakers in Spain &mdash; even though the numeral system actually originated much further east!

We all know how this sytem works. We have 10 *digits*: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$ and $9$. The $0$ is special &mdash; we'll come back to it later &mdash; but the rest of the digits are just the first 9 numbers in our numeral system. What happens when we try to count past nine? Simple! We roll over to the next decimal place: so from $9$, we then go to $10$, $11$, $12$ and so on. Once we hit $19$, we go up to $20$, $21$, $22$ and so on. Only when we hit $99$ do we go to the next decimal place: $99$, $100$, $101$. Everybody knows this stuff. Too easy!

Have you ever thought about how they came up with this numeral system in the first place? For example, why did they decide to go with 10 digits?

## Digits

Here's a big hint: what can the word *digit* mean? It has multiple meanings, doesn't it?

In math, a digit is a number. In anatomy, a digit is a finger ... and, wouldn't you know it, there are as many digits as humans have fingers! You remember counting on your fingers, and that's certainly something people were already doing in every society before anyone thought to start writing numbers down.

If the 10 digits in our numeral system just come from the fact that we have ten fingers, then what would our numeral system look like if humans had a different number of fingers?

Imagine a parallel universe just like ours, wth the same history as ours, where humans came up with the same Arabic numeral systems as us, except for one key difference: in the parallel universe, humans have 2 fingers instead of 10! In that world, they'd probably end up with only two digits: $0$ and $1$, rather than our fuller $0$ through $9$.

How would counting look for those imaginary people?

Well, the first number would probably seem familiar: good old $1$.

But try to count past $1$ and, oops, we're already out of digits &mdash; mathematically and anatomically! So, of course, we move to the next number place: the number after $1$ is ... $10$!

But wait! &mdash; you might say &mdash; what about all the missing numbers? You can't just jump from $1$ to $10$! Well, it's tricky, but there actually *aren't* any missing numbers! Our two-fingered friends have all the same numbers we do; they're just labelling theirs differently. It's like they're speaking a slightly different numeric language than us &mdash; and their language means something different by $10$ than we do. (It's sort of like [false friends](https://en.wikipedia.org/wiki/False_friend), but for numbers instead of words.)

Hopefully that sort of makes sense so far? Let's try to keep counting. What are the next few numbers, as our two-fingered friends would write them? The answer is below, so get out a sheet of paper now and try to write down the next few numbers *before* you move on and see what the right answer. Remember ... you're counting like you normally do, but the only digits you have to work with are $0$ and $1$! Don't use $2$ through $9$!

Gave it a shot already? Want to see the answer? Okay, here it is: $1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"), $101$ ("five"), $110$ ("six"), $111$ ("seven"), $1000$ ("eight"), $1001$ ("nine"), $1010$ ("ten"). Did you get it right?

Hopefully you're starting to get it now! Assuming you read the last chapter of this book carefully, you might already see where this is going: you're counting in binary! If you got the example above correct, you're ready to move on. If not, here's a quick table to help you see how binary numbers map to the way we write numbers:

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

We just saw how our numeral system (Arabic numerals) is flexible on how many digits you decide to use. If you use 10 digits, you get the system we all learned in school. If you use 2 digits, you get binary!

The number of digits one of these systems uses is called the numeral system's **basis**, or sometimes its "**radix**." The basis (radix) of our system is 10, so we call it "base 10." When we write in binary, we use the same Arabic numeral system, but we use a basis (radix) of 2. So we call binary "base 2."

> Do you find the term "base 10" confusing? If not, well, maybe you should! How can we rightfully call our numeral system "base 10" if the whole problem is disagreeing what "10" means? Wouldn't our imaginary two-fingered friends from the previous example *also* call their system "base 10"?
>
> The truth is, yeah, they probably would. That's why, when we talk about a system's basis, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in school, and not "10" as our imaginary friends would mean it.

You can count using Arabic numerals in any basis. For example, here are a few of the smallest possible bases:

| Name       | Basis  | Digits                            |
| ---------- | ------ | --------------------------------- |
| Binary     | Base-2 | $0$, $1$                          |
| Trinary    | Base-3 | $0$, $1$, $2$                     |
| Quaternary | Base-4 | $0$, $1$, $2$, $3$                |
| Quinary    | Base-5 | $0$, $1$, $2$, $3$, $4$           |
| Senary     | Base-6 | $0$, $1$, $2$, $3$, $4$, $5$      |
| Septenary  | Base-7 | $0$, $1$, $2$, $3$, $4$, $5$, $6$ |

Did you notice there's no "unary" base-1 system in the table above? That's because binary is the smallest basis that works in the Arabic numeral system: a basis is a way of writing "$10$," so you have to have at least two digits: $0$ and $1$.

We also could have kept going. In fact, you can even use a basis higher than 10! For example, as we'll see later in the book, it's sometimes useful in computing to represent numbers in base-16, which is called **hexadecimal**. When we count in hexadecimal, we need more than 10 digits, so after $9$ we start borrowing letters from the alphabet: $0$, $1$, $2$, $3$, $4$, $5$, $6$, $7$, $8$, $9$, $A$, $B$, $C$, $D$, $E$, $F$, $10$, $11$, ..., $19$, $1A$, $1B$, ..., $1F$, $20$ ,$21$ and so on.

Feeling good about binary so far? If not, I encourage you to look at the three-columned table above. If you're still not getting it, Google is your friend! From now in this book, I will assume you're reasonably comfortable counting in binary.

## Why are we doing this again?

Alright, time to come up for air! That was a quick primer in binary ... now, let's remind ourselves, why were we doing all this again? Why did we care about binary?

Remember from first chapter that we're going to build a computer out of electricial circuitry using the concept of *switching*. A switch has two possible states: on or off. Binary is a numbering system with two possible digits: $0$ or $1$. Because of this, we're going to be able to come back later and represent binary numbers in circuitry using switches, by using one switch per digit of a binary number.

Sound familiar? Phew!

Back in school, I'm sure you learned to count in your very first math classes. Then, once you figured out counting, you moved on to doing basic math: addition, subtraction and so on. We're going to do the same thing in this book for binary: now that you know how to count, let's start doing some math on binary numbers!

On the next page, we'll learn some of the most basic math you can do on binary numbers: the math of single-digit binary numbers. Let's go!