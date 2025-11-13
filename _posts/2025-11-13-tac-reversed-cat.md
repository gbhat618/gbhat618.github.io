---
layout: post
title: `tac` as `cat` reversed
date: '2025-11-13 23:45:00 +0530'
categories:
  - Technology
tags:
  - linux
  - terminal
  - command
comments: []
---

<div style="text-align: center;">
  <img src="/assets/images/2025-11-13-upside-down-cat" alt="Upside down cat image" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
  <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
    <em>Image by ChatGPT</em>
  </div>
</div>

Learnt just few minutes ago - there exists a command in linux `tac` which does the reverse of `cat`. What a nice and perfect name!

```
→ cat dummy.txt
Lorem Ipsum is simply dummy text of the printing and typesetting industry.
Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.
It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
```

```
→ tac dummy.txt
It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.
It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.
Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.
Lorem Ipsum is simply dummy text of the printing and typesetting industry.
```

Man page: https://man7.org/linux/man-pages/man1/tac.1.html (also see `rev` linked in the man page, such nice tools!)

