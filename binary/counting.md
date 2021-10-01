---
layout: chapter
title: Binary&#58; Counting
---

> To gain some insight about binary, let's think about our normal numbering system first
>
> Here's our system: we have 10 digits &mdash; $0$ to $9$ &mdash; and the first few numbers are those digits.
>
> Then what happens next? We start over, and move to the next decimal place. $10$, $11$, $12$, ...
>
> When we hit $19$, do we go to $100$? Nope! We go to $20$. At $29$ we go to $30$ and so on.
>
> Eventually, we repeat this process until we get to $99$, and when we add $1$, what happens? We roll over the 1s place to $0$ and add $1$ to the 10s place; but the 10s place is also 9! So that has to roll over too, and we have to now move up to the 100s place. So it goes $99$, $100$, $101$
>
> You have probably known this for a very long time. Why did we spell it out here? Well, I want you to think a little about how we ended up at the numbering system we use
>
> Why do we have 10 digits?
>
> Here's a big hint: what can digit mean? In math, it's a number ... in anatomy, it's a finger! Of course, we have 10 digits because we have 10 fingers.
>
> What would our numbering system look like if we had a *different* number of fingers?
>
> Imagine a world identical to ours, with a history identical to ours, except for one key difference: in this imaginary world, humans have 3 fingers instead of 10. In that world, what would their numbering system end up looking like?
>
> Like us, they chose to have as many digits as they have fingers. Unlike us, they only have three fingers. So they would only have come up with three digits: $0$, $1$ and $2$.
>
> How would these people count in that system?
>
> Well, the first couple numbers would seem familiar: $1$, $2$. But, ah, now they're out of digits &mdash; both mathemtical and anatomical digits &mdash; so what are they going to do next? The same thing we do when we run out of fingers: move to the next number place! So their counting goes $1$, $2$, $10$.
>
> Okay, you might ask, but what about all the missing numbers? You can't just jump from $2$ to $10$! Well, it's tricky, but actually there are no missing numbers! Our three-fingered friends have all the same numbers we do; they're just labelling theirs differently. 
>
> It's like they're speaking a different numeric 'language' than us &mdash; one that means something different by "10" than we do. (It's sort of like [false friends](https://en.wikipedia.org/wiki/False_friend), but for numbers instead of words.)
>
> In case it helps, look at the following table. In this table, we're going to count, starting from 1, in both number systems at the same time. Every row in this table is the *same number*, just written differently.
>
> > Insert table from the old draft
>
> In summary, our three-fingered friends use the same numbering system we do, except they only have three digits ($0$ $1$ $2$) whereas we have 10 ($0$ $1$ $2$ $3$ $4$ $5$ $6$ $7$ $8$ $9$). We could always use their system to count, if we had a reason to, just as they could always use our system if *they* wanted to. The numbering system is the same either way; the only thing that differs is the number of digits being used.
>
> The number of digits between 0 and 10 is called the numbering system's **basis** or sometimes its **radix**. The basis (radix) of our system is 10, so we call it "base 10," whereas our imaginary friends' system has a basis (radix) of 3, so we call it "base 3."
>
> > By the way, if you find the term "base 10" terribly confusing, you're completely justified. How can we call our system "base 10" if the whole problem is defining what "10" means? Wouldn't our three-fingered friends also call *their* system "base 10?"
> >
> > The answer is yup, they probably would. That's why, when we talk about bases, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in school, and not "10" as our imaginary friends would mean it.
>
> If you get how counting in base-3 works, and how base 3 numbers relate to base-10 numbers, then congrats, you already get binary: binary is just base-2!
>
> In base-2, we only have two digits to work with: $0$ and $1$. Like with both numbering systems above, you move to the next place when you run out of digits. In binary, though, there are so few digits that this happens very frequently: $1$, $10$, $11$, $100$, $101$, $110$, $111$, $1000$, $1001$, $1010$.
>
> Show a final table that compares base-10, base-3 and base-2 counting.
>
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





> Should we mention that a bit is a binary digit? Should we mention bytes too? Or save that for later? I think it might be relevant soon, so we may want to hit it now.