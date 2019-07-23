---
layout: post
title: Connecting to MARCC
slug: connecting
description: Instructions for connecting to MARCC

title: Connecting to MARCC
teaching: 10
exercises: 20
questions:
- "How can I connect to MARCC?"
objectives:
- "Install or find `ssh` software on your computer."
- "Log on to Blue Crab."
keypoints:
- "All you need to connect to MARCC is a shell and a copy command. There is more than one way to bake a cake."
---

## What is MARCC?

The Maryland Advanced Research Computing Center ([MARCC](https://www.marcc.jhu.edu/)) is a shared academic high-performance computing (HPC) facility. MARCC hosts a [supercomputer](https://www.top500.org/site/50589) named "Blue Crab" which is available to researchers at Johns Hopkins University and the University of Maryland. In this section, you will learn how to connect to Blue Crab so that you can use it for your research.

> ## What's in a name?
> We will refer to "MARCC" and "Blue Crab" interchangably for this course, and until MARCC builds a new machine.
{:.callout}

## Software required to connect

Blue Crab is a remote computer which requires a secure connection and two-factor authentication (2FA). To accomplish this, we will use [secure shell](https://en.wikipedia.org/wiki/Secure_Shell) to dial in. First, we will briefly cover installation instructions for the following machines.

1. [Windows 10](#win10)
2. [Windows 7](#win7)
3. [MacOS](#macos)

### Windows 10 {#win10}

Windows 10 includes `ssh` [by default](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_overview), hence no installation is necessary. To use `ssh`, open the "command prompt" from the search box in the task bar and type `ssh` to get started.

![The command prompt in Windows.]({{page.root}}/fig/snap-win-prompt.png){:.normimg}

### MacOS {#macos}

Similarly, MacOS ships with a terminal that requires no additional installation. Open a spotlight search with <kbd>command</kbd> + <kbd>spacebar</kbd> and type `terminal` to open 

![The MacOS terminal.]({{page.root}}/fig/snap-mac-terminal.png){:.normimg}

### Windows 7 {#win7}

FIXME

### Other terminals

FIXME

