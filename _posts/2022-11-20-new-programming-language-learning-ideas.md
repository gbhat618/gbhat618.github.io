---
layout: post
title: "New Programming Language Learning Ideas"
date: '2022-11-20 18:07:47 +0530'
categories:
  - Blog
tags: []
comments: []
---

When we already have experience in one programming language like Python or Java by writing software for a few years, learning a new language should become easier.  

However several questions arise:

- If I want to learn a programming language, how do I measure my success levels?  
- One can get to too low level in programming languages, so how much should I learn? For an application engineer, knowing how to develop a modular application relatively quickly is probably the benchmark.  
- Then, what does it take to be able to write a good modular application?  

This blog post contains some notes along this thought process...

## Level 1: Basic constructs

Knowing the syntax of the language, data types, loops, if-else statements, writing methods, and classes and how to run the code, built-in data structures — more or less a ++ version of “Hello World”.

With this one can do problem-solving for algorithm data structures, probably pass Level 1 interviews. After doing some online tutorials, basic programming, and problem-solving this can be achieved.

## Level 2: Simple scripts or small APIs

Knowing how to work with data exchange between:

- file systems  
- databases  
- network calls  
- multi-threading and multiprocessing  

The idea here is that the code is not just stdin → stdout or in-memory based problem solving, but interacts with other software interfaces.

Some simple exercises can be:

- Reading and writing to files in different formats (JSON, CSV, etc.)  
- Making network calls (GET/POST, etc.)  
- Making simple SQL queries to the databases for CRUD operations  

This helps get automation tasks done using the programming language. At this point, we can start seeing some clear returns for putting in the time to learn the language.

## Level 3: Back to Basics

After clearing Level 2 exercises, we should try to cover blind spots and bridge knowledge gaps.

Maybe it is only possible by reading a book on “language reference.” These books should cover pretty much everything the language has to offer with clear code examples and discussions:

- Syntax, data types, default values, etc.  
- Modules and packages: Structuring constructs for hundreds of lines of code  

Examples:  

- Python: `import`, `__init__` files, `PYTHONPATH`, etc.  
- Java: `import`, modules, packages, access specifiers, etc.  
- Multithreading and multiprocessing  
- Network APIs  
- File APIs  
- Built-in data structures  

It will make things crystal clear as past experience gets reinforced and several questions get answered.

Example books:  

- *Java: The Complete Reference*  
- *The Go Programming Language*  
- *C++: The Complete Reference*  

### Level 3a: Idioms of the language

Just like natural languages, programming languages have their own idioms or best practices to do specific things — e.g., creating a hashmap from a list, filtering a list of items.  

This is where sayings such as “Pythonic way of doing” or “the Java way of doing” come in.

This can be learned by following good blogs and articles, or books that serve as handbooks to refer to from time to time.

Example books:  

- *Python Tricks: A Buffet Of Awesome Python Features*  
- *Python Cookbook*  
- *Effective Java*  

### Level 3b: Tooling, packaging system, and common libraries

To scale to professional development and large projects, one needs to know the tools. Some are transferable across languages, some are ecosystem-specific.

1. Common tooling: git, GitHub, debugging basics, IDEs, documentation reading, etc.  
2. Specific tooling: build tools, package repos, installation, paths, etc.  
   - Java: Maven, Gradle, Maven Central  
   - Python: PyPy, pip  
3. Common libraries:  
   - Java: Apache Commons, Google Guava, Jackson, args4j  
   - Python: requests, csv, json, pandas  

The best way to learn is to work on at least 3–4 real-world projects.

## Level 4: Frameworks that are platforms

Frameworks often act as platforms for certain job roles. Developers spend most of their time in these frameworks/platforms (ORMs, web API layers, CLI frameworks, etc.).  

Relevance is **job-profile specific** and learning-as-you-go, but doing practice and courses helps.

Examples:  

- Java: Spring, Spring Boot, Hibernate, Quarkus, Micronaut  
- Python: Flask, SQLAlchemy, Django, pandas, NumPy, TensorFlow, Jupyter Notebook  

## Level 5: Profilers, benchmarking, debugging, and performance best practices

This is for senior developers deeply into software development in that language.  

Performance and memory issues require awareness of tools and measurement methods. General best practices are relevant across languages, but tools are mostly specific:

- Java: jstack, jmap, Eclipse MAT, JProfiler, signal handling  
- Python: cProfile, kCacheGrind, Snakeviz  

There is more to think about in this part…

## Level 6: Internals of the language, memory models, and concurrency

- Memory model of the language  
- Garbage collection or memory management APIs  
- Concurrency patterns: threads, green threads, coroutines, processes  
- Inter-thread and inter-process communication  
- Thread/process lifecycle, performance, and memory costs  

## Level 7: Core development

....
