---
layout: post
title: Software Engineer Learning Resources
date: '2022-11-13 16:58:34 +0530'
categories:
  - Blog
tags: []
comments: []
---

Today, computers and technology have become part of every aspect of human life. It touches all the sectors—medical, food, transportation, travel, entertainment, sports—just about everything. In such a world, where software applications are a crucial component of daily operations, it is the responsibility of software engineers to get software applications right.

As we see how software impacts other sectors, there is always innovation going on within. There are always better tools and technologies, improvements in techniques, and discoveries being made across the software lifecycle.

The lifecycle of software is:

- **Design and development**: creating the software itself using programming languages and databases, coming up with architecture, writing software, doing testing, etc.
- **Delivery**: depends on the mode of consumption—could be end-user mobile/web apps, SaaS products, desktop apps, embedded software in cars, software in safety-critical environments, etc.
- **Maintenance and support**: deals with aspects of bug fixing and additional feature integrations.

Internal to each of these aspects, there are further stages and tools involved to efficiently develop reliable systems and build confidence in their working.

As we can realize, developing reliable software is a complicated task, and we (the world) need just that. Make no mistake: computers are purely unbiased—if there is a bug, it is a bug and it's going to blow up. Therefore, it is the responsibility of every software engineer to be invested in self-learning, improve skills, adapt to new tools and techniques, and develop reliable, good software.

There are going to be some engineers who are involved in creating the tools and platforms (system software developers), while other engineers are going to be creating real-world software. It is important for everyone to be engaged in self-learning, get skilled, and develop confidence.

These notes contain some of the resources I have used for my learning… Most of it is primarily helpful for Software Engineers with experience of **1–3 years**.

## Concepts

- **Programming**
  - C or C++ — Knowing these helps low-level concepts of programming, such as pointers and memory allocation/deallocation.
  - Java, C#, or Go — Helps understand concepts like language runtime/VM, garbage collection, and patterns for developing large-scale applications.
  - Python or Ruby — Useful for rapid scripting to automate tasks.
  - SQL — There is a lot more to SQL than `SELECT *`. Learn basics like `GROUP BY`, CTEs, and window functions. Some people think they know SQL all around, but probably haven't seen [this yet](https://learnsql.com/blog/draw-sql-recursive-queries/).

- **Data Structures and Algorithms**
  - Knowing when to use which data structure.
  - Having a good grip on time complexity and space complexity and making it a habit to notice these in any code we see or write.
  - Learn the main/common algorithmic patterns.

- **Operating Systems**
  - The best way to learn an OS is by using a flavor of Linux.
  - Some basic must-knows are:
    - Monitoring CPU, memory, and disk usage
    - Difference between processes and threads
    - Monitoring various aspects of a single process, like its own CPU, memory, network, and disk usage
    - Difference between memory and virtual memory, etc.

- **Computer Networks**
  - OSI model and the basics of how the web works: DNS resolution, TCP/IP, sockets, and common L7 protocols
  - A fair idea of networks and subnets
  - Concepts of NAT and firewall basics; tools such as `traceroute`, `ping`, `telnet`, Wireshark, etc.

- **Databases**
  - RDBMS — PostgreSQL, MySQL, Oracle, Microsoft SQL (any one of these)
  - NoSQL — Document DBs: MongoDB/CouchDB; KV DBs: Bigtable/HBase (any one)
  - Big Data — BigQuery, Hadoop, Spark (a fair idea is enough)

## Tools

- IDEs (IntelliJ, PyCharm, VS Code, Eclipse, NetBeans — any)
- Text Editor: Sublime, VS Code
- Version control: Git
- Code development workflows: GitHub, pull requests, code reviews, etc.
- Task management: Jira, Trello, etc.
- Cloud: GCP, AWS, Azure (any one). You can learn using free credits and later pay a small amount.
- Linux terminal and shell scripting: be comfortable using the terminal and writing small scripts.

## Coding Problem Solving

- LeetCode
- HackerRank

## Websites

Technical blogs of tech companies (a few examples; almost every famous tech company has one):

- <https://developers.googleblog.com/>
- <https://engineering.fb.com/>
- <https://blog.twitter.com/engineering/en_us>

Other open-source news and blogs (examples only; there are many more credible websites):

- <https://lwn.net/>
- <https://news.ycombinator.com/>
- <https://www.opensourceforu.com/>
- <https://www.python.org/blogs/>
- <https://www.infoq.com/>
- <https://www.thoughtworks.com/radar>

Tutorial portals worth following for new articles:

- <https://realpython.com/>
- <https://www.baeldung.com/>
- <https://www.freecodecamp.org/>

## Video Courses

1. [CS50](https://www.edx.org/course/introduction-computer-science-harvardx-cs50x?index=product&queryID=cf8d204f04ac94a7fa51c22ad614494b&position=1&linked_from=autocomplete) — Highly recommended for CS fundamentals. For people coming from a non-CS background (or if the college degree didn’t teach anything—which is common), this course helps cement fundamental concepts.
2. [Google’s course on Data Structures](https://www.udacity.com/course/data-structures-and-algorithms-in-python--ud513)
3. [MIT lectures on data structures](https://www.youtube.com/watch?v=HtSuA80QTyo&list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)
4. [Java — Udemy course I found useful](https://www.udemy.com/course/master-practical-java-development/). There may be better/free ones on edX, YouTube, or Coursera.
5. [Linux — Udemy course I found useful](https://www.udemy.com/course/linux-administration/). There may be better/free ones on edX, YouTube, or Coursera.

One should find such courses by previewing and randomly checking a few lectures to ensure the course or playlist is good.

## YouTube

Some must-watch talks:

- [Uncle Bob SOLID principles](https://www.youtube.com/watch?v=zHiWqnTWsn4&t=557s)
- [A Philosophy of Software Design — John Ousterhout — Talks at Google](https://www.youtube.com/watch?v=bmSAYlu0NcY)
- [Kelsey Hightower fireside chat at DevRelCon San Francisco](https://www.youtube.com/watch?v=wCwLOHMtkpo)
- [The Elephant in the Architecture — Martin Fowler (ThoughtWorks)](https://www.youtube.com/watch?v=u_LnubpBDCA)
- [Career Advice for Programmers • Trisha Gee • GOTO 2013](https://www.youtube.com/watch?v=LlAn452X4Lc)
- [Ken Thompson is a singularity (Brian Kernighan)](https://www.youtube.com/watch?v=fL2QwyxcJ5s)

Some great videos:

1. [YOW! 2018 Brendan Gregg — Cloud Performance Root Cause Analysis at Netflix](https://www.youtube.com/watch?v=tAY8PnfrS_k)
2. [How Did We End Up Here? • Todd Montgomery & Martin Thompson • GOTO 2015](https://www.youtube.com/watch?v=oxjT7veKi9c)
3. [Mining Bitcoin with pencil and paper](https://www.youtube.com/watch?v=y3dqhixzGVo)

Playlists

- **Python**
  - [Corey Schafer playlists](https://www.youtube.com/c/Coreyms/playlists)
  - [Real Python playlists](https://www.youtube.com/c/realpython/playlists)

- **Java**
  - [JavaGuides](https://www.youtube.com/c/JavaGuides)
  - [Java (official)](https://www.youtube.com/user/java)
  - [The Pub House Network](https://www.youtube.com/channel/UCDesXEioPr9dZKIWYYimCSA/playlists)
  - [Java Brains](https://www.youtube.com/c/JavaBrainsChannel)
  - [yCrash](https://www.youtube.com/channel/UCM-yObJ7pBjEy1wJMq5bDdw)

- **Resume and Communication**
  - [Sonal Bahl — Career Strategist](https://www.youtube.com/c/SuperChargeYourself)
  - [Professor Heather Austin](https://www.youtube.com/c/ProfessorHeatherAustin)
  - [MasterTalk](https://www.youtube.com/@MasterTalks)
  - [Joseph Tsar](https://www.youtube.com/@ttsar)

Individuals’ channels:

- [Errichto](https://www.youtube.com/c/Errichto)
- [Nick White](https://www.youtube.com/c/NickWhite)
- [Gaurav Sensei](https://www.youtube.com/c/GauravSensei)
- [Tech Dummies Narendra L](https://www.youtube.com/c/TechDummiesNarendraL)
- [sudoCODE](https://www.youtube.com/c/sudoCODE)
- [Engineer Man](https://www.youtube.com/c/EngineerMan)
- [The Coding Train](https://www.youtube.com/c/TheCodingTrain)
- [Techquickie](https://www.youtube.com/c/Techquickie)
- [Scott Hanselman](https://www.youtube.com/c/shanselman)
- [Imtiaz Ahmad](https://www.youtube.com/c/ImtiazAhmad007)
- [Gary Explains](https://www.youtube.com/c/GaryExplains)

Good channels:

- [Computerphile](https://www.youtube.com/user/Computerphile)
- [Talks at Google](https://www.youtube.com/c/talksatgoogle)
- [TFiRio](https://www.youtube.com/c/TFiRio)
- [TechWorld with Nana](https://www.youtube.com/c/TechWorldwithNana)
- [ScyllaDB](https://www.youtube.com/c/ScyllaDB)

## Podcasts

These can be found in Google Podcasts:

- The InfoQ Podcast
- Coding Blocks
- Command Line Heroes
- Python Bytes
- Talk Python To Me
- The Changelog
- The Cynical Developer
- Inside Java
- Base.cs
- CppCast
- The Cloudcast
- Masters of Scale
- Scaling Postgres
- Software Engineering Radio
- This Week In Linux

## GitHub Repos

1. Developer Roadmap — <https://roadmap.sh/>
2. <https://github.com/kamranahmedse/developer-roadmap>
3. Coding Interview University — <https://github.com/jwasham/coding-interview-university>

## Books

**Technical**

- [The Complete Software Developer’s Career Guide](https://www.amazon.com/Complete-Software-Developers-Career-Guide-ebook/dp/B073X6GNJ1)
- [Cracking the Coding Interview](https://www.amazon.com/Cracking-Coding-Interview-Programming-Questions/dp/0984782850)
- [Clean Code](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)
- [Python Tricks](https://www.amazon.com/Python-Tricks-Buffet-Awesome-Features/dp/1775093301)
- [Java: The Complete Reference](https://www.amazon.com/Java-Complete-Reference-Eleventh/dp/1260440230)
- [Effective Java](https://www.amazon.com/Effective-Java-Joshua-Bloch/dp/0134685997)
- [Java Concurrency in Practice](https://www.amazon.com/Java-Concurrency-Practice-Brian-Goetz/dp/0321349601)
- [Head First Design Patterns](https://www.amazon.com/Head-First-Design-Patterns-Brain-Friendly/dp/0596007124)
- [A Philosophy of Software Design](https://www.amazon.com/Philosophy-Software-Design-John-Ousterhout/dp/1732102201)
- [Refactoring](https://www.amazon.com/Refactoring-Improving-Design-Existing-Code/dp/0201485672)
- [The SRE Book](https://sre.google/sre-book/introduction/)
- [Kubernetes Up and Running](https://www.oreilly.com/library/view/kubernetes-up-and/9781491935668/)

**Personality Development**

- [Atomic Habits](https://www.amazon.com/Atomic-Habits-Proven-Build-Break/dp/0735211299)
- [The 7 Habits of Highly Effective People](https://www.amazon.com/Habits-Highly-Effective-People-Powerful/dp/0743269519)
- [Eat That Frog!](https://www.amazon.com/Eat-That-Frog-Great-Procrastinating/dp/162656941X)

## Apps

- [Taro](https://play.google.com/store/apps/details?id=com.randomappsinc.techcareergrowth&hl=en&gl=US)
