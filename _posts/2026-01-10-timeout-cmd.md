---
layout: post
title: timeout command in linux
date: '2026-01-13 19:48:00 +0530'
categories:
  - Technology
tags:
  - linux
  - terminal
  - command
comments: []
---

<div style="text-align: center;">
  <img src="/assets/images/2026-01-10-timeout-cmd.jpg" alt="Kid in timeout corner" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
  <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
    <em>Image - somewhere from Internet</em>
  </div>
</div>

The `time` command had always been useful to me, to check how long an activity took, used it a lot for database activities (such as index creation, or migrations).

```bash
$ time sleep 10

real    0m10.068s
user    0m0.001s
sys     0m0.003s
```

Just this week, I was so happy to learn the `timeout` command to kill upon exceeding certain duration.

Example below, terminates command expected to take 10s after 5s.

It's silent if explicitely not asked to report.
```bash
$ timeout 5 sleep 10
$ echo $?
124
```
enable verbose
```bash
$ timeout -v 5 sleep 10
timeout: sending signal TERM to command ‘sleep’
$ echo $?
124
```

per man page (https://man7.org/linux/man-pages/man1/timeout.1.html)
```
   Exit status:
       124    if COMMAND times out, and --preserve-status is not specified
```
