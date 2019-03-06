---
title: Ignore Files without using .gitignore
description: Ignore files without using .gitignore
date: '2017-04-24T16:00:00.000Z'
---

![Git](./git.jpeg)

## Problem

I discovered a cool aspect about git while writing some scripts today. I had written a bunch of a scripts for myself and wanted to keep. However, I didn’t want to push them, I just wanted to keep them locally. I also didn’t want to add a bunch of random personal file paths into the `.gitignore` file.

This is likely to happen to any developer. You could have written some test or automation scripts that you want to keep around but wouldn’t necessarily want to commit directly into a shared repository.

You also wouldn’t want to pollute your `.gitignore` file with paths to files only you have access to. This could end up leading to confusion among your current or future colleagues.

## Solution

> Thankfully git offers a simple solution to getting around this issue through the use of the `.git/info/excludes` file.

The `.git/info/excludes` file works the same exact way as your `.gitignore` file except it isn’t tracked by git and exists only within your local repo. This is perfect if you want to prevent git from tracking personal files/directories without changing your `.gitignore` file.

## Final note

If you haven’t had the chance to delve into the `.git` directory yet, you should peak around. This is the source for all of git’s magic and if you take the time to look through this directory you’ll come out with a better understanding of <a href="https://git-scm.com/book/en/v2/Git-Internals-Git-Objects" target="_blank">Git's plumbing</a> and how it actually works. This could save you from a bunch of wasted time and needless frustration in the future.

![XKCD Git](./xkcd-git.png)
