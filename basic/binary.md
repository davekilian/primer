---
layout: chapter
title: A Basic Computer&#58; Binary
---

A computer is a programmable calculator, so if we're going to build one, we're going to need to deal with numbers. Just about every modern computer uses binary to represent numbers, so understanding how computers work means learning a thing or two about binary. If that sounds intimidating don't worry! Binary looks weird, but it's easier to understand once you get the basic idea &mdash; like everything else in computing, binary was invented for humans, by humans, to be convenient. Once you get the basic idea it won't seem so magic anymore.

Binary is an example of a number system: it's just a way of writing numbers down. There are many number-writing systems, each providing its own way of writing down each number. Different systems have different ways of representing the same number: for example, if I asked you to write down the number of days in a week, you'd probably write $7$, but if I asked an ancient Roman to do the same thing, the Roman (using Roman numerals) would probably write that as $VII$. Two writing systems, but it's the same number either way!

> You might now be trying to visualize the number $7$ is without finding a way to write it down. Don't do this ... this might be an interesting mathematic or philosophical question, but you're liable to burn a lot of time only to end up more confused than before!
>
> Numbers are tied to your numbering system the same way words are tied to languages: two languages can have two different words that mean the same thing, but to have a word you need a language.

There are many numbering systems, and there have been more throughout history. The system you and I learned in school is based on people using fingers to count. (Have you ever wondered why there are 10 digits? Or noticed the word "digit" can either mean a number or a finger?) We use one digit to represent each of our fingers, rolling over to $10$ on our last finger. But what if humans had fewer fingers? Or more?

Imagine what our numbering system would be like if humans only had three fingers. We'd start by counting off, 1 ..., 2 ..., and then we're already on our last finger. So 10? Then we'd need to roll over to keep counting: 1, 2, 10, 11, 12, 20, 21, 22, 100, 101, 102, 110, ...

The critical thing to understand is that our three-fingered friends didn't skip any numbers when they went from 2 to 10! They just mean something different by "10" than we do. The situation is the same as with the example earlier with Roman numerals &mdash; but this time it's more confusing because their system and our system sometimes overlap, The problem is similar to that of [false friends](https://en.wikipedia.org/wiki/False_friend) in languages and translation.

In case it helps make things more clear, here's a quick chart comparing our numbering system to theirs; each row of the table gives the different ways the different systems write the same number:

| Their System | Our System |
| :----------: | :--------: |
|      0       |     0      |
|      1       |     1      |
|      2       |     2      |
|      10      |     3      |
|      11      |     4      |
|      12      |     5      |
|     100      |     6      |
|     101      |     7      |
|     102      |     8      |
|     110      |     9      |
|     111      |     10     |
|     112      |     11     |
|     120      |     12     |
|     121      |     13     |
|     122      |     14     |
|     200      |     15     |
|     201      |     16     |
|     202      |     17     |
|     210      |     18     |
|     ...      |    ...     |
|     222      |     26     |
|     1000     |     27     |
|     ...      |    ...     |

So their system is the same as ours, but they have fewer digits between 0 and 10, so they have to roll over more often. The number of digits between 0 and 10 is called the system's **basis** or sometimes its **radix**. The basis (radix) of our system is 10, so we call it "base 10," whereas our friends' system has a basis (radix) or 3, so we call it "base 3." This is because our system has 10 digits (0, 1, 2, 3, 4, 5, 6, 7, 8 and 9) and their system only has three (0, 1 and 2).

> If you find the term "base 10" terribly confusing, you'd be justified. How can we call our system "base 10" if the whole problem is disagreement over what "10" means? Wouldn't our three-fingered friends also call *their* system base 10?
>
> Yup, they probably would. That's why, when we talk about bases, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in grade school.

If you get how counting in base 3 works, and how base 3 numbers relate to base 10 numbers, you pretty much get binary already: binary is just base 2!

Imagine once again that humans evolved with a different number of fingers, but this time imagine we only ended up with two fingers. These human only have the digits 0 and 1, so their version of 10 is the same as our version of 2. Our two-fingered friends would count like this:

<center>1, 10, 11, 100, 101, 110, 111, 1000, 1001, 1010, ...</center>

Get it?

To make sure you understand correctly, try to keep counting and come up with the next few numbers in the sequence. Don't move onto the next paragraph until you've done so, because the next paragraph will give you the answer.

The answer is: 1011, 1100, 1101, 1110, 1111, 10000, ... If you got that right, then congratulations: you understand binary numbering!

Since we're taling about bases already, there's another numbering system you might want to know if you spend time working on computers: hexadecimal. So far we've been talking about numbering systems with fewer than 10 digits; hexadecimal is an example of a numbering system with *more* than 10 digits. There are 16 hexadecimal digits, which means "10" in hexadecimal is equal to "16" in our system.

To represent hexadecimal, we have a problem: we only invented 10 unique digits, but we need 6 more to represent hexadecimal numbers. By convention, the way you do this is usually to start grabbing letters from the alphabet to stand in for the missing digits. So counting in hexadecimal (or "hex," as it's sometimes called) looks liek this:

<center>1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, 10, 11, 12  ...</center>

Can you guess the next few digits in the sequence? Try to count to, say, the 32nd hexadecimal number. Don't move on to the next paragraph until you have an answer you think is right.

The rest of the sequence is: 13, 14, 15, 16, 17, 18, 19, 1A, 1B, 1C, 1D, 1E, 1F, 20. Perfect!

For completeness, here's a table of all the different numbering systems we talked about so far, showing how you count in each row-by-row:

| Base-2<br>(Binary) | Base-3<br>(Ternary) | Base-10<br>(Decimal) | Base-16<br>(Hexadecimal) |
| :----------------: | :-----------------: | :------------------: | :----------------------: |
|         0          |          0          |          0           |            0             |
|         1          |          1          |          1           |            1             |
|         10         |          2          |          2           |            2             |
|         11         |         10          |          3           |            3             |
|        100         |         11          |          4           |            4             |
|        101         |         12          |          5           |            5             |
|        110         |         100         |          6           |            6             |
|        111         |         101         |          7           |            7             |
|        1000        |         102         |          8           |            8             |
|        1001        |         110         |          9           |            9             |
|        1010        |         111         |          10          |            A             |
|        1011        |         112         |          11          |            B             |
|        1100        |         120         |          12          |            C             |
|        1101        |         121         |          13          |            D             |
|        1110        |         122         |          14          |            E             |
|        1111        |         200         |          15          |            F             |
|       10000        |         201         |          16          |            10            |
|       10001        |         202         |          17          |            11            |
|       10010        |         210         |          18          |            12            |
|        ...         |         ...         |         ...          |           ...            |
|       11010        |         222         |          26          |            1A            |
|       11011        |        1000         |          27          |            1B            |
|        ...         |         ...         |         ...          |           ...            |

That's binary! There really isn't any more to it.

There's some additional terminology around binary which is worth noting if you study computing. The term **bit** refers to a single digit of a binary number (in fact, the term "bit" is short for "binary digit.") The term **byte** refers to an 8-digit binary number (i.e. a byte is 8 bits). Bytes exist because a single bit has only two possible values, $0$ and $1$, which means you can't do a whole lot with a single bit. Some very old computers had a different number of bits per byte (4 and 6 were common examples), but those computers are long since extinct; nowadays, when someone says "byte" you're very safe in assuming that means exactly 8 bits.

When storing large amounts of data, it's often useful to store lots of bytes together. When talking about huge collections of binary numbers, we use the [standard SI prefixes](https://www.nist.gov/pml/weights-and-measures/metric-si-prefixes) (kilo, mega, giga, tera, and so on). However, instead of using increments of 1,000 like SI calls for, we use increments of 1,024 (1,024 is close to 1,000 and is also a power of 2, which is useful in several cases). The following table descries this in a bit more detail:

| Unit          | Meaning         | Number of Bytes       | Number of Bits        |
| ------------- | --------------- | --------------------- | --------------------- |
| Kilobyte (KB) | 1,024 bytes     | 1,024                 | 8,192                 |
| Megabyte (MB) | 1,024 kilobytes | 1,048,576             | 8,388,608             |
| Gigabyte (GB) | 1,024 megabytes | 1,073,741,824         | 8,589,934,592         |
| Terabyte (TB) | 1,024 gigabytes | 1,099,511,627,776     | 8,796,093,022,208     |
| Petabyte (PB) | 1,024 terabytes | 1,125,899,906,842,624 | 9,007,199,254,740,992 |

> The choice of 1,000 vs 1,024 bytes for scaling is a source of confusion in computing. For example, hard drive manufacturers typically use increments of 1,000 since it makes their drives sound bigger; but most software uses 1,024 bytes, meaning that when you plug in a hard drive that was advertised as 100 GB (100,000,000,000 bytes), software reports it as being significantly smaller (about 97 GB, because $100*(1000/1024) \approx 97$).
>
> There have been attempts to get people to use different units to describe 1,000-byte vs 1,024-byte increments, but so far none has taken off very widely.

Okay, you might say, now we know binary, but why did we bother with all this? I did say that computers are designed by humans, for humans, to be convenient to other humans ... how could binary numbering be convenient for humans who are only familiar with base 10?

The main reason we use binary is because it's easy to represent using electricity. As we'll see very soon, the calculator that makes up modern computers is driven by tiny electrical wires and the components that connect them. By convention, we usually define wires as 'digits' of a binary number, where we represent a binary 1 by sending electricity through the wire, or a binary 0 by not sending electricity through the wire. In other words, a binary 1 corresponds to a wire being "switched on," and a binary 0 corresponds to "switched off." Then, to represent a multi-digit binary number, we just use more wires. 

Here's an example of a circuit consisting of 8 wires, which represent the 8-digit binary number 01010010:

![Example circuit which uses binary to represent numbers](./binary.circuit.svg)

In the diagram above, each of the thin vertical lines represents a wire with no electricity traveling across it; the thick lines represent wires with electrical current flowing through. Each wire is labeled with a 0 or 1 depending on whether or not there's current traveling through the wire; if we read the wires from left to right, we get the binary number 01010010​, which would be 82 if you wrote it in base-10.

On the next page, we'll start looking at what you can do with binary numbers represented on electrical circuits in this way, eventually building ourselves a simple electricity-based digital calculator!

