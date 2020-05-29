---
layout: chapter
title:
---

This is a book for anyone who's really wanted to understand how computers work: real, modern computers, like the one you just used to download this book.

It didn't always take a whole book to describe how computers work. The first computers may have been large and expensive, but they were also pretty simple from a conceptual standpoint: a single person could design, build, program and operate these kinds of machines single-handed, if they had the time (and money). But these aren't the kinds of computers we use anymore: to design a build the kind of computer you're using now, you'd need a small team of specialists.

As computers get better and better, they also get more and more complex. All this complexity has had a funny effect on the field of computers and computing: people who program computers, and even people who design and build computers often don't have a general idea of how their computers works end to end. If computers seem like magic to the people who build them, how would a non-technical computer user every hope to see a computer as anything but?

Well, in this book we're going to dispel some of that magic! Computers may be complex, but if there's one thing about computers working in our favor, it's that this complexity was invented entirely by humans, for humans. This isn't like studying a messy biological system; there's a logical progression of ideas and accomplishments you can follow to get from nothing to modern computing. In this book, we're going to  retrace that path, at least roughly, to give you the broad shape of what computers are and how they work.

## Why Read This Book?

**Sheer curiosity**: Why not? Maybe you just don't know much about how computer works but wanted to know, at least the main rundown. If you've looked for answers online before, you might be frustrated at how quickly explanations resort to handwaving. (Oh, the number of times I've read that the "CPU" is the "brain" that "does the computing" &mdash; Isn't that the main part of how my computer works? How could we gloss over that?!)

**Getting into the field**: Computing is a hot area of public and private research and development. Being good at computer software or hardware can land you a cushy job with a fat salary and nice perks. There are lots of boot camps out there to help you get started with code, but those generally don't dedicate much if any time helping you understand what happens when your code runs &mdash; and knowing that is crucial to writing the best code out there (It's also where the *really* good money is.)

**Improving as a programmer**: If you're a software developer, you may have realized that you have a tenuous grasp on what happens when your code runs, even if you're pretty productive knowing what you do. Understanding the big picture and being able to zoom in and out from the lowest levels of computation to full networked distributed app and web development will help you 

**Making new kinds of computers**: There's a sort of invisible crisis in computers nowadays: we're stuck in a basic design from around the 70s and 80s, mostly because that was the point computers got too complicated for any one person to design and build alone. To get bigger and faster computers (like in the cloud), smaller and lighter computers (like mobile devices and wearable computers), or even new kinds of computing nobody's thought of yet, we're eventually going to need to bend or even break away from this design. To do that, we need to understand how the entire machine works.

## What We'll Cover

We'll start at the most basic level: what a computer is, what it does, and how you would build a simple computer using electrical circuitry. Then we'll build up to modern computers, covering topics like

* How your computer represents numbers, text, images, sound, video and more
* How developers program computers, and how these programming tools work
* The hardware devices inside your computer, and how software uses them
* Operating systems, the basic software that most programs are built on top of
* How computers network together, and how the Internet works
* Advanced topics and recent developments in the field

Our goal will be to walk you through these major moving pieces and see roughly how they work and how they fit together. One thing we *won't* do is delve into the nitty-gritty specifics: if you understand in general how these things work and what the goal is, there's a lot of great reference material already out there to help you learn the details. My goal with this book is to make sure you're well-enough equipped to dive deeper in any of these topics you find interesting.

This is book is written for anyone to read and understand. You don't have to be a programmer to understand this book (although if you are, you'll likely find this a quicker and easier read).

## About the Author

I'm a software engineer with a background in writing high-performance code in areas like graphics and distributed storage. I'm currently working on performance and optimization problems for Azure.

I wrote this book because nothing like it exists (as far as I know), and I think it ought to. Back in high school I used to spend hours trawling the Internet reading basic explanations of everyday inventions and tools, and I remember every explanation of computers falling flat: ending too early, lots of handwaving, and feelings I didn't really understand anything. I eventually ended up on a research mission to understand how my computer works, and my continued failure to find a simlpe, straightforward explanation dragged me down deeper and deeper into the field &mdash; which brings me to today, more than a decade later, working on these things professionally :-)

This book is a culmination of over a decade of learning about and working on computers at every level, sometimes piecing things together from historical context and occasionally reading tea leaves. I hope that reading this book will give you an idea of how hardware and software are co-designed to create all the technology you use day-to-day.

This book is also an attempt to help provide the Internet with more free resources for intermediate-level software development. I taught myself to program in high school, using a variety of different free resources I'd found online and a good bit of practice. Later, I had the great fortune of being able to get a computing degree from [an Ivy League institution](https://www.brown.edu). What I found along the way was that the free resources I had found were very rudimentary, and that there simply wasn't any content out there for intermediate-level developers looking to get to the next level. While college was what did that for me, not everyone can luck into the experience I did &mdash; so this book is an attempt to provide some of the resources I wish I had when I was trying to self-teach way back when.

## About the Book

You can always find the latest version of this book at [https://www.davekilian.com/primer/](https://www.davekilian.com/primer). If you find any typos, mistakes or anything that just could have been written better, please don't hesitate to let me know by filing an issue at [https://github.com/davekilian/primer/issues](https://github.com/davekilian/primer/issues). For minor corrections, feel free to fork the repo ([https://githubcom/davekilian/primer](https://github.com/davekilian/primer)) and submit a pull request with a fix. 

Ready? Then let's get started!