---
title: "Linux Overview: What is Linux?"
summary: "Overview of the Linux Desktop."
date: 2024-03-03
draft: false
categories: ["Linux"]
series: ["Linux-Overview"]
series_order: 1
---

## Series Overview: What is Linux?

Many years ago, I would search up "Linux vs Ubuntu" and "Linux kernel vs Linux operating system". As a total newbie at the time, many of the explanations involved more terms that I did not know.
I eventually learned about operating systems and kernels formally, as part of the amazing [operating systems course](https://artsci.calendar.utoronto.ca/course/csc369h1) taught by [Dr. Angele Demke Brown](https://www.cs.toronto.edu/~demke/bio.shtml).
After having developed a basic version of POSIX threads and a very simple file system, I felt confident enough to revisit "Linux vs Ubuntu" posts on Stack Overflow. (Note: You do not need to have written your own version of pthreads or a file system to understand these concepts)

My motivation to write this series is based on my initial struggles of understanding what Linux is and any related concepts, and I hope
to provide an easier onboarding experience to them.

## A Very Brief History

Understanding the history of Linux is important, as it provides a great motivaiton for open source development. Linux was
developed by Linus Torvalds, in his attempt to provide (himself and anyone that may have been interested) a free alternative to the commercially available Unix OS kernel. A decade later, Linux wound up competing with Microsoft in the enterprise software market. Long story short, Microsoft got smoked; a billion dollar proprietary software company could not compete against an open source product. Today, Microsoft Azure incorporates Linux to a degree and they have publicly shifted their opinion of Linux. There are plenty of articles that dig deeper on both the history of Linux and its competition against other open source software and proprietary software companies.

## What exactly is Linux?

Linux is an operating system kernel. A kernel is the core of an operating system, which at a high level is a mediator between user level applications and the hardware. Every application you have interacted with relies on the operating system, and by extension the kernel, to launch, process, and execute your actions. Here is the [Linux GitHub page](https://github.com/torvalds/linux), which contains all the code for the Linux kernel. Freely available for anyone to see and contribute to. Imagine if Bill Gates had a website with the code for Windows or Steve Wozniak for Apple.

## Conclusing Remarks

At a high level, Linux is a freely available operating system kernel. It has applications in desktops, servers, embedded devices,
etc. The next couple articles will talk about Linux as a desktop operating system.
