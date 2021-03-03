---
layout: chapter
title:
---

This is a book about how computers work: real, modern computers, like the one you just used to load this page.

That we need a whole book to *really* describe how computers work says something about just how far we've come. There was a time when all you'd need to 'get' how computers do their job was maybe a few articles. Even if they were huge, power-hungry monsters, the first practical computers were conceptually simple enough that one person (with time and funding) could feasibly design, build, program and operate one alone.

Well, no more &mdash; modern computers are so complex, they'd probably be unrecognizable to the people who built the original computers. Nowadays you not going to find any one person building an entirely new computing system from scratch; in fact, you'd be lucky to find anybody in the  field who can even walk you through the basic steps involved in a task like downloading this book (which, we'll see, is not so basic at all). This might sound like a looming crisis, but it's actually one of computing's greatest accomplishments: nobody has to know everything the computer does, and yet we're still productive at making new computers that do new things faster and better.

And yet, there come times when it is useful to understand the big picture of how your computer does all the things it does. And for that, you'll need a whole book &mdash; this one!

## Why Read This Book?

**Sheer curiosity**: Why not? Maybe you just don't know much about how computer works but wanted to know, at least the main rundown. If you've looked for answers online before, you might be frustrated at how quickly explanations resort to handwaving. (Oh, the number of times I've read that the "CPU" is the "brain" that "does the computing" &mdash; if I wanted to know how my computer works, wouldn't I want to understand the computing part of the computer?)

**Getting into the field**: Computing is a hot area of public and private research and development. To be blunt, being good at computer software or hardware can land you a cushy job with a fat salary and nice perks. There are lots of boot camps out there to help you get started with code, but these generally don't help you understand the code that runs your code, or how code works together with hardware &mdash; and the people who work on those parts of the system are the ones making the *really* good money.

**Improving as a programmer**: You don't need to understand the platform beneath you when you write apps, but it sure helps to understand what's going on 'under the hood' when your code runs. If you're finding that your preferred programming language or the APIs you use seem arbitrary, it might help to peel back the interface and understand how they work and why they're designed that way. After all, computers are designed by humans, for humans, and everything was designed to work a certain way for a reason.

**Making new kinds of computers**: To get bigger and faster computers (like in the cloud), smaller and lighter computers (like mobile devices and wearable computers), or even new kinds of computing nobody's thought of yet, we're going to have to continue to evolve our computing architectures and maybe even invent some new ones. The first step of doing that is to understand what we already have today.

**Dispelling the magic**: A lot of the tech that we build on and have come to see as immutable laws of computing's nature are simply the practical decisions of long ago. The cryptic tomes of computing won't seem to cryptic if you know what kind of computers we had back then and how they were evolving.

## What We'll Cover

We'll start at the most basic leveis, what it does, and how you would build a simple computer using electrical circuitry. Then we'll build up to modern computers, covering topics like

* How your computer represents numbers, words, images, sound, video and more
* How developers program computers, and how these programming tools work
* The hardware devices inside your computer, and how software uses them
* Operating systems, the basic software that most programs are built on top of
* How computers network together, and how the Internet works
* Advanced topics and recent developments in the field

Our goal will be to walk you through these major moving pieces and see roughly how they work and how they fit together. We're not going to delve nto the nitty-gritty specifics: the hope is, if you have a general framework of pieces and how they fit together, you can use a lot of the great reference material that's already out there to learn the details.

This is book is written for anyone to read and understand. You don't have to be a programmer to understand this book, but if you know how to program a lot of the concepts we'll cover will already be familiar, making this a quicker and easier read.

## About the Author

I'm a software engineer with a background in writing high-performance code in areas like graphics and distributed storage.

I wrote this book because nothing like it exists (as far as I know), and I think it ought to. Back in school I would sometimes trawl the Internet reading basic explanations of everyday inventions and tools, and I remember every explanation of computers falling flat: ending too early, lots of handwaving, and feelings I didn't really understand the pieces and how they fit together. As I continued to hit walls in my mission to understand how computers '*really*' work, I was pulled deeper and deeper into the weeds &mdash; and more than a decade later, now I'm working on building these things :-)

This book is a culmination of over a decade of learning about and working on computers at many levels, sometimes piecing things together from historical context and occasionally reading tea leaves. I hope that reading this book will give you an idea of how hardware and software are co-designed to create all the technology you use day-to-day.

With this book I also hope to provide a good, free resource for programmers who know the ropes and want to advance. I taught myself to program in school, using a variety of different free resources I'd found online and a good bit of self practice. Later, I had the great fortune of being able to get a computing degree from [an Ivy League university](https://www.brown.edu). One of the first things I learned there was how rudimentary my self-taught background really was, and many 'unknown unknowns' I had yet to be exposed to. I value my education and I realize everyone can't have the same luck I did in getting one of that caliber; so one of my goals with this book is to help self-teachers get exposed to the things I don't think I would ever have stumbled into on my own.

## About the Book

You can always find the latest version of this book at [https://www.davekilian.com/primer/](https://www.davekilian.com/primer). If you find any typos, mistakes or anything that just could have been written better, please don't hesitate to let me know by filing an issue at [https://github.com/davekilian/primer/issues](https://github.com/davekilian/primer/issues). For minor corrections, feel free to fork the repo ([https://githubcom/davekilian/primer](https://github.com/davekilian/primer)) and submit a pull request with a fix. 

Ready? Then let's get started!