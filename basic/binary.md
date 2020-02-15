---
layout: chapter
title: A Basic Computer&#58; Binary
---

Since a computer is, at its heart, a programmable calculator, we're going to need to deal with numbers. Just about every modern computer uses binary to represent numbers, so understanding how computers work means learning a thing or two about binary. As we'll soon see, binary is easier to understand than it might first appear!

Binary is a numbering system, which just means it's a way of writing numbers down. There are many number-writing systems, each providing its own way of writing down the same number. For example, if I asked you to write down the number of days in a week, you'd probably write $7$, but if I asked an ancient Roman to do the same thing, the Roman would use Roman numerals to write that as $VII$. It's the same number either way &mdash; the difference is in how you choose to write the number down.

The numbering system you and I learned in school is based on people using fingers to count. (Have you ever wondered why there are 10 digits, or noticed the word "digit" can either mean a number or a finger?) We use one digit to represent each of our fingers, rolling over to $10$ on our last finger. But what if humans had fewer fingers? Or more?

Imagine what our numbering system would be like if humans only had three fingers: we'd start by counting off 1, 2 and 10 on our fingers, and then rolling over to count further. Sort of like this: 1, 2, 10, 11, 12, 20, 21, 22, 100, 101, 102, 110, ...

Here's the kind of weird thing: when our three-fingered friends skipped ahead to 10, they weren't skipping any numbers; instead, their definition of 10 is different from ours. The number that our three-fingered friends would call 10, we would call 3; and the number we would call 10, our three-fingered friends would call 101. Like with Roman numerals versus ours, we're talking about the same number, but we're using (slightly) different systems to write them down.

The number of digits a numbering system like ours has to work with is called a **basis**, or sometimes a **radix**. We call our numbering system "base 10," whereas we'd use the term "base 3" to describe the numbering system our three-fingered friends use.

> You might find this naming convention kind of confusing: how can we call our system "base 10" if the whole problem is that we and our alternate timeline friends don't agree on what what "10" means? Wouldn't the alternate timeline humans also call their system base-10?
>
> Yup, they probably would. That's why, when we talk about bases, we always use *our* numbering system. So when we say our numbering system is "base 10," we always mean the 10 you learned in grade school. 

Binary numbering works similarly to what we just described; in fact, binary is just a base-2 numbering system. To understand binary, you might want to imagine humans evolved to only have two fingers, so their version 10 is our version of 2. Our two-fingered friends would count like this:

<center>1, 10, 11, 100, 101, 110, 111, 1000, 1001, 1010, ...</center>

To make sure you understand correctly, try to guess the next few numbers if you would continue counting. Don't move onto the next paragraph until you've done so, because the next paragraph will give you the answer.

The answer is: 1011, 1100, 1101, 1110, 1111, 10000, ...

If you got that right, then congratulations: you understand binary numbering!

Since we're taling about bases already, there's another numbering system you might want to know if you spend time learning about computers: hexadecimal. So far we've been talking about numbering systems with fewer than 10 digits (or, should I say, "10 base-10" digits); hexadecimal is an example of a numbering system with more than 10 digits. There are 16 hexadecimal digits, which means "10" in base-16 is equal to "16" in base-10.

To represent hexadecimal, we have a problem: we only invented 10 unique digits, but we need 6 more to represent hexadecimal numbers. By convention, the way you do this is usually to start co-opting letters of the alphabet. So to count in hexadecimal (or "hex," as it's sometimes called):

<center>1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F, 10, 11, 12  ...</center>

Can you guess the next few digits in the sequence? Try to count to, say, 32 base-10. Don't move on to the next paragraph until you have an answer you think is right.

The continuation of the sequence is: 13, 14, 15, 16, 17, 18, 19, 1A, 1B, 1C, 1D, 1E, 1F, 20. Perfect!

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

Congratulations on learning binary!

Okay, you might say, now we know binary, but why did we bother? Why would people build computers that use binary numbering when base-10 is more familiar to everyone and easier to work with?

The main reason we use binary is because it's easy to represent using electricity. By convention, we usually define wires as 'digits' of a binary number; each wire is a binary 1 if there's electricity flowing across the wire, or a binary 0 if there's no electricity flowing across the wire. In other words, a binary-1 corresponds to "switched on," and a binary-0 corresponds to "switched off," accordingly.

Using multiple wires, then, we can represent a binary number of any size, along as we have enough digits (i.e. wires). Here's an example of a circuit consisting of 8 wires, which represent the 8-digit binary number 01010010:

![Example circuit which uses binary to represent numbers](./binary.circuit.svg)

In the schematic diagram above, each of the thin vertical lines represents a wire with no electricity traveling across it; the thick lines represent wires with current. Each wire is labeled with a 0 or 1 depending on whether or not there's current traveling through the wire; if we read the wires from left to right, we get the binary number 01010010​, which would be 82 if you wrote it in base-10.

On the next page, we'll start looking at what you can do with binary numbers represented on electrical circuits in this way, eventually building ourselves a simple electricity-based digital calculator!