---
layout: chapter
title: A Basic Sketch&#58; Numbers
---

So, how are we going to work with numbers in electronic circuitry?

The key idea we'll use is *switching*. A switch turns an electric circuit on or off &mdash; for example, you probably use a light switch to turn the lights on or off at your place every day. More precisely, a switch controls the flow of electricity: when it's on, the switch *completes* a circuit so that electricity can flow through it. When it's off, a switch *interrupts* the circuit, preventing electricity from flowing on through the switch.

> Diagram

How is switching useful for doing calculations on numbers? It's easier to see if you count using *binary* numbering. In our regular numbering system, there are ten digits, $0$-$9$; in binary there are just two digits: $0$ and $1$. In our normal numbering system and in binary alike, you move to the next number place when you run out of digits in the current place. As such, the first few binary numbers look like this:

​	$1$ ("one")<br>
​	$10$ ("two")<br>
​	$11$ ("three")<br>
​	$100$ ("four")<br>
​	$101$ ("five")

If it's not immediately clear how binary works, don't worry: we'll take a closer look at binary soon. For now, it's important to know that any number can be represented in binary, and you only need two digits: $0$ and $1$.

Binary is useful when you're working with switches because binary only uses two digits &mdash; $0$ and $1$ &mdash; and a switch only has two states &mdash; on and off. That lets us use a switch to represent a binary digit: we can use "switched off" to represent $0$ and "switched on" to represent $1$ in circuitry. To represent a binary number with multiple digits, we use multiple switches; for example, if we wanted to represent a 4-digit binary number, we'd need to use 4 switches &mdash; one for each digit.

For example, let's say we wanted to represent the number 6 in binary. We'd start by counting to six in binary:

​	$1$ ("one"), $10$ ("two"), $11$ ("three"), $100$ ("four"),  $101$ ("five"), $110$ ("six")

It looks like we need three digits, so we'll use three switches:

* The 1s place switch, which would be switched off (because the 1s place of $11\underline0$ is $0$)
* The 10s place switch, switched on (the 10s place of $1\underline10$ is $1$)
* The 100s place switch, swithced on (the 100s place of $\underline110$ is $1$)

In practice, you might want to be able to store much larger numbers; for example, with eight switches, you could store any number from 0 to 255. If we wanted to use those eight switches to store the number six ($110$), all we need to do is set the switches as described above, and then set all the remaining switches off. That is, the 1,000s place switch should be off (set to $0$), as should the 10,000s place, the 100,000s place, and so on. We might write the resulting configuration as $00000110$ to remind us of all those extra switches that are all turned off.

Hopefully that gives you a feel for how to represent numbers in binary using circuitry. If things still feel a little fuzzy, that's ok &mdash; remember we'll go in greater depth over the next chapter of this book.
