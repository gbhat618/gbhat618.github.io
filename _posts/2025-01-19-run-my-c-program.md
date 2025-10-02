---
layout: post
title: "Just run the C program"
date: '2025-01-19 06:32:27 +0530'
categories:
  - Programming
tags:
  - C
  - Bash
  - Linux
---

I was writing a few simple C programs with an engineering student, in the process, we were making a lot of small changes to observe how the program behaved.

For example:

- adding or modifying the print statements here and there
- removing certain condition or comment out a block of code to see how it behaved
- sometimes making mistakes and program wouldn't compile

Simple C program execution is:

```bash
gcc myprogram.c
./a.out
```

Occassionally I would forget to re-compile before executing `./a.out`. So I started doing:

```bash
gcc myprogram.c -o myprog && ./myprog
```

Now this improved two things:

- No need to type 2 commands
- Never forgetting to compile and later noticing "ah! I missed to compile before executing"

Then I thought, this too is combersome, instead I should have a tool that could "re-compile" and "execute" everytime. After all these are lab programs, they hardly have any noticeable compilation time.

So my desired command would be:

```bash
run myprogram.c
```

This `run` should support two things:

- compiler arguments; such as `-lm` for programs involving `math.h`
- cli arg inputs for the executable; example case is, `./a.out myarg1 myarg2`

If these two are supported, then pretty much all engineering lab programs would work with the `run` tool.

This `run` tool can be a shell script:

```bash
#!/bin/bash

if [ "$#" -lt 1 ]; then
    echo "Usage: run [compiler-options] <file.c> [program-arguments]"
    exit 1
fi

while [[ "$1" != *.c ]]; do
    compile_args+=("$1")
    shift
done

file="$1"
shift
program_args=("$@")

if [ ! -f "$file" ]; then
    exit 1
fi

if gcc "${compile_args[@]}" "$file" -o "${file%.c}"; then
    "./${file%.c}" "${program_args[@]}"
else
    echo "Compilation failed."
fi
```

Alright, now the script is ready, all I have to do is, ensure it is on the path thus accessible from anywhere in my laptop.

```bash
# create and paste the script content
sudo vim /usr/local/bin/run

sudo chmod +x /usr/local/bin/run
```

Test it, write a simple hello world program `hello.c`

```bash
➜  ~ run hello.c
Hello, World!
```

In case there is a mistake in compilation, it simply shows the output directly from `gcc` command execution:

```bash
➜  ~ run hello.c
hello.c: In function ‘main’:
hello.c:4:34: error: expected ‘;’ before ‘}’ token
Compilation failed.
```

I believe it is important to have these kind of re-usable toolings for one self - so that the focus can be on what really matters.

In this case atleast, we were trying to implement concurrency concepts by program, wanted to focus on the code design, logic, thinking about the control flow (not fighting with gcc commands).
