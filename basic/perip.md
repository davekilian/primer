---
layout: chapter
title: A First Sketch&#58; Peripherals
---

We have covered a lot of ground in this chapter. We have designed what, even today, still seems like a technical marvel, and filling in the details might already sound a little daunting. Despite all of the amazing work we have done together throughout this chapter, I am sad to report we, so far, have managed to design a largely useless computer. A technical marvel with about zero practical real-world applications.

Womp, womp. What went wrong?

Well, there's no way for a person to *use* this computer! There's no way to input data. There's no way to program the computer. There's no way to get the results of any computation we do. How is a human, in the real world, supposed to use this thing?

We need to add a few **I/O** devices to our computer! "I/O" stands for "input/output." The term refers to the fact that each device has one of two functions: to collect information from a human (input) or to send information to a human (output). Some devices do both!

Examples of input devices include keyboards, computer mice, touchscreens, cameras and microphones. Each of these provides some way for users to provide information to a computer: by touch, by sound or just by being seen.

Examples of output devices include displays, printers, speakers and vibrators (haptic feedback). Each of these provides some way for computers to provide information to a user: by sight, sound or vibration.

There are also I/O devices that interface with other computers instead of the real world. Network cards and cell modems are I/O devices that allow a computer to communicate with other computers over wired and wireless networks. Additionally, there are I/O devices that store and retrieve data; these allow the computer to save data even across reboots and power loss.

All of these devices are present in modern computers &mdash; desktops, laptops, phones and more &mdash; and they're all critical to turn basic computing elements into fully usable computing platforms. Even so, these devices aren't part of the core of the computer: they're the link between the core and the rest of the world. That these devices occupy the periphery between the core and the rest of the world is why these devices are often called **peripherals**.

You might wonder how these things work: how do peripherals interact with the core of the computer, and the programs running on that programmable core?

There are a few different ways to do this. One is to provide additional, peripheral-specific instructions that allow programs to interact with the periphals. This is simple, but not very flexible. Another is to provide a programmable interface based on reading and writing the peripheral's own memory, which is separate from RAM. This is complex, but highly flexible. We'll cover this later in the book.

We're now very close to finished with our basic sketch of a computer. The last thing we need to figure out is the moment of genesis: what happens when you turn the computer on? How do we get all this other stuff going? Who put all these programs in memory in the first place?