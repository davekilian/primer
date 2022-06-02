---
layout: chapter
title:
---

<div class="visible-md visible-lg">
  <h1>Primer: How Computers Work</h1><p>By <a href="https://www.davekilian.com">Dave Kilian</a></p><hr>
</div>

This is a book for people who want to know how computers work!

In this book, we'll delve deep inside a computer and see how everything is put together. You'll come away with a very good idea of what goes into a real, modern computer &mdash; like the one you're using to read this book right now! However, you won't learn anything about how to *use* or *program* computers.

Even though we'll be covering some technical concepts, I aim to make this an easy read. You do not need to be a coder to understand this book. But, the more you know about code, the more I think you'll get out of this book!

This book is a culmination of over a decade of learning, collecting notes, and (occasionally) reading some tea leaves. I hope you enjoy it!

## Why write this book?

I'll be up front with you: you do not need this book to be good at using computers. You can even be a pretty great coder without knowing almost anything in this book!

Take a look at the device you're using to read this book. Every single aspect of your device, from what you see, to the hardware inside, to the software that it runs, was designed by people. Computers don't come from nature &mdash; *we* made them! Many, many people have collectively poured millions of hours of their lives into designing the device you're using. The next time someone tells you a computer is cold, metal, unfeeling &mdash; you can tell them your computer is one of the most human things ever to exist!

The funny thing is, even though computers are a 100% human invention, people seem to have a hard time explaining how they work. Just try googling for information about how computers work &mdash; I think you'll find that you end up knowing more about computers, but won't get that feeling you really *get* them. You won't be able to tell someone what's *really* going on when you open your laptop and go watch some videos on YouTube.

The point of this book is to help you *get* computers. 

Every explanation of how computers work, including the one in this book, has to find a way to grapple with the ridiculous complexity of a real computing device. Normally, authors tackle this by picking some aspect they consider to be 'core' to the design and just explaining those. I'm going to do something a little different. This book will give you the *whole* picture, but in very little detail. That's why this book is called *Primer*!

My goal is for you to walk away with a clear enough picture of what goes into a computer, physically and in software, to go off and fill in the details for the aspects of the design that's interesting to *you*. 

## Why read this book?

Okay, you ask, so what's in it for me?

**Satisfying your curiosity**: Maybe, like me once, you just want to know how computers work? I'll vouch &mdash; It's worth learning! Underneath a mountain of arcane terms and alphabet soup acronyms are some surprisingly simple and profound ideas. Every aspect of your computer has been designed by humans, for humans, to be easy to understand by humans. Even if you never work on a computer, you'll learn some profoundly cool ways of dealing with and managing big, complex systems.

**Getting into the field**: Computing is a huge, lucrative field, and even in 2022 it seems to only be continuing to heat up. There are plenty of resources out there to help you get started coding &mdash; something this book will not help you with &mdash; but starting out with what you learn in this book will put you ahead of people who just know how to use one or two coding tool.s

**Improving as a developer**: I won't lie, you can get very far as a coder with very little information about how computers run your code. Even so, knowing the platform beneath your code is a superpower! Every thing you learn about how your computer works will help you write more elegant, faster code, write it faster, and debug it more easily.

**Making new kinds of computers**: To get bigger and faster computers (like in the cloud), smaller and lighter computers (like phones and wearable computers), or even new stuff nobody's thought of yet, we're going to have to evolve our computing architectures and maybe even invent some new ones. The first step of that is to understand what we already have, and why what we have is the way it is.

## What We'll Cover

We'll start at the most basic level: what a computer is, what it does, and how you would build a simple computer using electrical circuitry. Then we'll build up to modern computers, covering topics like

* How your computer represents numbers, words, images, sound, video and more
* How developers program computers, and how these programming tools work
* The hardware devices inside your computer, and how software uses them
* Operating systems, the basic software that most programs are built on top of
* How computers network together, and how the Internet works
* Advanced topics and recent developments in the field

Our goal will be to walk you through these major moving pieces and see roughly how they work and how they fit together. We're not going to delve nto the nitty-gritty specifics: the hope is, if you have a general framework of what the pieces are and how they fit together, you can use a lot of the great reference material that's already out there to learn the details. There's plenty of stuff out there for beginners, and many articles for professionals; with this book, I'm hoping to help you bridge the gap between those two extremes.

This is book is written for anyone to read and understand. You don't have to be a programmer to understand this book, but if you know how to program a lot of the concepts we'll cover will already be familiar, making this a quicker and easier read.

No matter your skill level, I still recommend reading the book linearly. The chapters build off one another, so you might end up lost if you jump around or skip stuff.

## About the Author

I'm a teacher with a background in software engineering. I've written high-performance code for the cloud, and I have background experience in graphics, networking and distributed storage.

I wrote this book because nothing like it exists (as far as I know), and I think it ought to. Back when I was in school I would sometimes trawl the Internet for explanations of everyday inventions and tools, and I remember every explanation of computers falling flat: ending too early, lots of handwaving, and feelings I didn't really understand the pieces and how they fit together. I continued to hit walls in my mission to understand how computers '*really*' work, as I was pulled deeper and deeper into the weeds &mdash; and that's how I ended up working on building these things :-)

This book is a culmination of over a decade of learning about and working on computers at many levels, sometimes piecing things together from historical context and occasionally reading tea leaves. I hope that reading this book will give you an idea of how hardware and software are co-designed to create all the technology you use every day.

With this book I also hope to provide a good, free resource for programmers who know the ropes and want to become more advanced. I taught myself to program in school, using a variety of different free resources I'd found online and a good bit of self practice. Later, I had the great fortune of being able to study computing at Brown University. One of the first things I learned at Brown was how rudimentary my self-taught background really was, and many 'unknown unknowns' I had never been exposed to. I value my education greatly, and I realize everyone can't have the same luck I did in getting one of that caliber; so one of my goals with this book is to help self-teachers get exposed to the things I don't think I would ever have stumbled into on my own.

## About the Book

You can always find the latest version of this book at [https://www.davekilian.com/primer/](https://www.davekilian.com/primer). If you find any typos, mistakes or anything that just could have been written better, please don't hesitate to let me know by filing an issue at [https://github.com/davekilian/primer/issues](https://github.com/davekilian/primer/issues). For minor corrections, feel free to fork the repo ([https://githubcom/davekilian/primer](https://github.com/davekilian/primer)) and submit a pull request with a fix. Because of the way this book is published, all content is on the `gh-pages` branch instead of `main` or `master`.

Ready? Then let's get started!