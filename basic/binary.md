---
layout: chapter
title: A Basic Computer&#58; Binary
---

Since a computer is, at its heart, a programmable calculator, we're going to need to deal with numbers. Nowadays, just about every computer of note uses binary to represent numbers, so understanding how computers work means learning a thing or two about binary. As we'll soon see, binary is easier to understand than it might first appear!

Binary is a numbering system, which just means it's a way of writing numbers down. There are many number-writing systems, each providing its own way of writing down the same number. For example, you and I would use *our* numbering system to write down the number of days in a week as $7$, but an ancient Roman would use Roman numerals to write that as $VII$. Either way, it's the same number &mdash; the difference between the two is how you choose to represent that number in writing.

The numbering system you and I use is the **base-10** numbering system, also known as **decimal** numbering. Base-10 is called that because there are 10 digits (0, 1, 2, 3, 4, 5, 6, 7, 8 and 9) for each place. The first numbers are just 0-9; then, once we run out of digits, we start counting in the 10s place (10, 11, 12, ...), and once we run out of digits for the 10s place we start to count using the 100s place (100, 101, 102, ...), and so on.

Why 10, though? This system should work with any number of digits, after all. The main reason we use 10 more or less an accident: our numbering system evolved from earlier numbering systems which were based on people counting on their fingers and toes:

> *Traces of the anthropomorphic origin of counting systems can be found in many languages. In the Ali language (Central Africa), for example, "five" and "ten" are respectively* moro *and* mbouna: moro *is actually the word for "hand" and* mbouna *is a contraction of* moro *("five") and* bouna, *meaning "two" (thus "ten"="two hands").*
>
> *It is therefore very probable that the Indo-European, Semitic and Mongolian words for the first ten numbers derive from expressions related to finger-counting. But this is an unverifiable hypothesis, since the original meanings of the names of the numbers have been lost.*
>
> [The Universal History of Numbers](http://books.google.com/books?id=FMTI7rwevZcC) Wiley, 2000, pp 21-22, via [math.stackexchange.com](https://math.stackexchange.com/questions/8734/why-have-we-chosen-our-number-system-to-be-decimal-base-10)

It's possible to count in numbering systems that have more or fewer than 10 digits. For systems that have more than 10 digits, we often start using letters as additional digits; for example, a base-16 (hexadecimal) numbering system can be written using all 10 base-10 digits as well as the first 6 letters of the alphabet, for a total of 16 digits: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E and F (and after F comes 10, 11, ... 19, 1A, 1B, ...).

The following table demonstrates a few numbering system. Each row in the table is a single number, and each column denotes how these numbers are written in a different-base numbering system. Notably, the first column counts in binary (base-2), whereas the third column counts in our native numbering system (base-10):

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

If you understand how to count in binary now, well, that's really all there is to it!

A reasonable question to ask at this point is: why use binary to represent numbers on a computer instead of a more familiar numbering system like our beloved base-10?

The main reason we use binary is because it's easy to represent electronically. By convention, to represent a binary 1 on an electrical wire, the circuit sends some amount of current across that wire; to represent a binary 0, the circuit simply doesn't send any current across the wire. Using multiple wires, we can represent a binary number of any size, along as we have enough digits:

![Example circuit which uses binary to represent numbers](./binary.circuit.svg)

In the schematic diagram above, each of the thin vertical lines represents a wire with no current traveling across it; the thick lines represent wires with current. Each wire is labeled with a 0 or 1 depending on whether or not there's current traveling through the wire; if we read the wires from left to right, we get the binary number 01010010​, which would be 82 if you wrote it in base-10.

In practice, it's nearly impossible to send absolutely no current across a wire in an electrical circuit; instead,  the designer typically chooses some voltage $V$, such that a wire with voltage greater than $V$ is considered to be a 1 by convention, and a voltage less than $V$ considered by convention to be a 0. (If you're not familiar with the term "voltage," don't worry, we're about to define it on the next page of this book.)

On the next page, we'll take a look at what you can do with binary numbers represented on electrical circuits in this way.