---
layout: post
title:  "Useful Git Aliases and Commands"
date:   2017-05-09 08:30:00 +0100
categories: git aliases commands
excerpt: Some useful Git Aliases and commands
published: true
---

Below are some Git aliases that I've found useful

`co = checkout`

`cm = !git add -A && git commit -m`

`cm` combines git add with git commit so that you never forget to add new files again.

`lg = log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit --date=relative`

`lg` reates a nice log tree so you don't need to use SourceTree, pro-tip, use 'q' to exit the log.

`st = status`

And some Git commands that have come in handy.

`git commit --amend –C HEAD`

This is useful for when you've committed, but forgotten to add those new files.
