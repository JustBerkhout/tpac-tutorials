---
id: hpc-chosing-a-terminal-emulator
summary: What is a terminal emulator, how to chose one for your operating system.  Why putty is a poor choice for a beginning Linux user.
categories: hpc
tags: tutorial,ssh,installation,windows,osx,ubuntu,terminal
difficulty: 2
status: published
published: 2019-05-14

---

# Which SSH client? (TLDR: not putty)"
Duration: 1:00

## Overview

SSH, the secure shell, is often used to access a terminal on remote UNIX/Linux systems.  As the name suggests this is secure (encrypted) and it's used for very many things in the Linux world.

### What you'll learn
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet

### What you'll need

* A computer ..

## What is a terminal (??)
Duration: 1:00

OSX and Linux users have native terminals and as such this tutorial is largely irrelevant for them; however some interest might remain in the history of terminals, and my choice of some alternative terminal emulators.

However, at the time of writing, Windows users have no native terminal and so have to install a 3rd party one.  For various reasons beginning users are often told to use [putty][putty].

It's my assertion that the consequence of this is a needles over-complication exactly when new users should be having fun and learning.  I will assert a better option is [MobaXterm][mobaxterm] and I will explain why.

## A brief history lesson
Duration: 1:00

During the formative years of the computer industry, one of the early operating systems was called Unix. There have been literally dozens of UNIXes over the years, and the [UNIX family tree][unix-tree] makes for fascinating reading for those curious about such things.  Two notable and modern operating systems can draw roots back to Unix, notably Linux and OSX (via BSD).  This heritage will become relevant later on in this tutorial.

### Terminals

Originally Unix was designed to run as a multi-user system on mainframe computers, with users connecting to it remotely via individual terminals. These terminals were pretty basic by modern standards: just a keyboard and screen, with no power to run programs locally. Instead they would just send keystrokes to the server and display any data they received on the screen. There was no mouse, no fancy graphics, not even any choice of colour. Everything was sent as text, and received as text. Obviously, therefore, any programs that ran on the mainframe had to produce text as an output and accept text as an input.

Compared with graphics, text is very light on resources. Even on machines from the 1970s, running hundreds of terminals across glacially slow network connections (by today's standards), users were still able to interact with programs quickly and efficiently. The commands were also kept very terse to reduce the number of keystrokes needed, speeding up people's use of the terminal even more. This speed and efficiency is one reason why this text interface is still widely used today.

### Terminal emulators

Nobody uses real terminals anymore but the pattern was already set and it's still a powerful way to interact with computers.  When using a modern computer we can still leverage the simple power of terminals by using (or installing) a terminal emulator on our modern computer.  Once up and running they look and feel and largely operate the original physical terminals, except it's all done in software, it's emulated.

## Choosing a terminal emulator
Duration: 1:00

Your choice of terminal emulator will fundamentally effect your experience with the Linux world.  Made wisely and the terminal will provide you a world of flexibility and power.  Made poorly and you will experience incompatibility and frustration.  It's worth a moment to understand the difference between local and remote terminals.

### What's a local terminal?
If you have a local terminal, you can launch your terminal emulator and it immediately connects to your own local computer. You can then use Unix style commands straight away, no need to open a terminal session to a remote computer first.

This is extremely powerful and it is often overlooked by beginning users.  How simple is it to open a local terminal and type:

```bash
ssh jumpbox.tpac.org.au
```
Compared to a complex array of text entry boxes and buttons to try and achieve the same thing, not to mention file transfer or ssh key generation.

## Using Terminal on OSX and Ubuntu
Duration: 1:00

Computers based on UNIX/Linux have "native" Terminal emulators, which is why it's so easy for OSX/Linux users to operate with Linux.  

Recalling the history lesson, your operating systems have native terminal emulators (that is you don't need to install anything else).  For you guys this is quite a short tutorial.

OSX: You can simply start an application called *Terminal* and you're ready to go.  Once you're familiar with that you might like to try an alternative such as the versatile and powerful [iTerm2][iterm].

Ubuntu:  On 18.04 the default terminal is also called *Terminal* and this is developed by Gnome.  Again there are many (many) alternatives but i'll abuse my power and suggest my favorite [Terminator][terminator] which can be installed using apt.

Other Linuxes; if you're running one of these then you probably need no further help ;)

## Installing a Terminal on Windows

At the time of writing, Windows does not have a native terminal emulator (although this is rapidly changing in development builds of Windows 10).  That means in order for you to be able to work with Linux machines, you'll need to install some extra software.

### Why not putty then?

[Putty][putty] is one of the common terminal emulators for Windows does not provide a local terminal.  This leads to unnecessary complexity for new users who have to work out how to just connect to a remote computer before being able to run Unix commands.

In order to connect to a remote computer you must use putty.exe.  In order to create an ssh key you must use puttygen, and in order to copy files to a remote computer you need a different program again.

### What should i use?
Thankfully there is a sane option, simply use [MobaXterm][mobaxterm] and utilise the "Start local terminal" function.  MobaXterm actually installs a little package called [busybox][busybox] which gives you access to a heap of native linux commands right inside a convenient local terminal.

<!-- LINKS -->
[busybox]: https://busybox.net/about.html
[iterm2]: https://www.iterm2.com/downloads.html
[terminator]: https://gnometerminator.blogspot.com/
[ubuntuonwin]: https://www.microsoft.com/en-us/store/p/ubuntu/9nblggh4msv6
[ubuntuonwintut]: https://tutorials.ubuntu.com/tutorial/tutorial-ubuntu-on-windows
[putty]: http://www.putty.org/
[mobaxterm]: https://mobaxterm.mobatek.net/download.html
[unix-tree]: https://commons.wikimedia.org/wiki/File:Unix_history-simple.png
