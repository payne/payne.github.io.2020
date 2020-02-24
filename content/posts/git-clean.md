---
title: "git rebase"
date: "2017-02-07"
template: "post"
draft: false
slug: "/posts/git-rebase/"
tags:
  - "git"
  - "tools"
category: git 
description: "git fetch; git rebase origin/master"
---

## git rebase origin/master puts commits on top

1. git checkout feature-branch
1. git fetch
1. git rebase origin/master
This is better than the `git fetch && git merge origin/master` because it makes better looking git history logs.

So, `
[tig](https://jonas.github.io/tig/)` 
output looks nice and straight.


```
2017-03-03 12:06 Matt Payne         o [master] [origin/master] Guava is good                                                            
2017-03-02 00:10 Matt Payne         o Example test.  Needs writeup and a bunch of links.
2017-03-03 12:01 Matt Payne         o formatting
2017-03-03 12:00 Matt Payne         o Yay Guava!
2017-03-02 00:09 Matt Payne         o Start at logistic links
2017-02-04 23:46 Matt Payne         o Project ideas added.
2017-01-02 23:13 Matt Payne         o Better Java
2017-01-01 22:44 Matt Payne         o nice icons
2016-12-31 00:26 Matt Payne         o c9.io and emberJS
```

