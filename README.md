## Phoshell: Simplifying Programming with Forth inspired Stack Machine Shell

- Phoshell: A Universal, Extremely Lightweight "Embedded IDE" with Run-time Editing and Debugging Functionalities

- Phoshell: a Forth inspired, extremely lightweight stack machine shell, implementable in _ALL_ known programming languages.

:: Need to separate contents for senior vs. junior programmers. 

:: Highlight SIMPLIFYING PROGRAMMING.



1. Problem A: TELK &mdash; Time to Acquire Entry Level Knowledge


One of the biggest obstacles in working on a large scale open source repository such as Jitsi Meet is the lack of documentations for a new comer to familiarize with the respective modules and begin modifying the code.

Consider the following plan:

- Phoom link. We wish to create an Augmented Reality Conferencing App, based on Jitsi Meet Video Conferencing App.
  - We have successfully copied TFJS Mask function into JitsiMeetBlurEffect.js
  - We have used ChatMessage.js as entry point to Phoshell. 

:: describe A to Z of plan

:: mark notes with :: continuously refine notes between finished paragraphs.
:: number notes, easier to organize. remove numbers when finished.

- What are the hierarchy and relationships of the above and how does Phoshell relates them?



:: this is part of blindspots

Familiarizing with a new framework and the structure of a new project have become one of the most time consuming tasks when a programmer takes up a new project. The amount of time spent is especially significant for programmers wishing to get involved in a new open source project. This can make or break the decision for someone to join an open source project, as the time for familiarization could be a significant ratio to the total amount of time a programmer is able to engage in an open source project, usually on a part time basis, typically starting from single digit hours per week. 

By encapsulating framework and programming language specific details with RPN, programmers who are  unfamiliar with them may jump start and see results immediately.

Assuming exponential decay for number of interested programmers vs. time spent, then hopefully we may improve recruitments in open source projects exponentially by cutting down time needed to familiarize and see results. 


- AR conferencing app needs developers and users to move avatars. Use RPN, works for web, iOS and Android platforms.

Sample code: place avatar at 30 deg around table ...

Use ChatMessage text input to create new UI elements, debugging facilities, build Embedded IDE etc.



- 1.3 TELK

How long does it take for you to start modifying an app whose source code is available on GitHub or equivalent open source websites?

Need to compile, test run, find documentation and location and code to start modifying.

- 1.4 Solution to TELK

What if we can do it as and when app is run?

Why, who need this?

Need to write in such a way that readers who know nothing about Phoshell can understand. 

Nearest experience is Python shell? 

Use Python turtle graphics with and without Phoshell as example, to illustrate interactive input output with graphics. 

New title: the Last Mile in Computer Programming

Use this, can be understood by all:
- What if modifying any app can be done interactively via a textbook or equivalent element in the app itself?

Compare to nodejs ecosystem, third party contributing to building libraries.

Phoshell does not compete with existing Programming Languages and packaging frameworks, but compliments them in the "last mile" (explain telephone line analogy). 

Highlight what nodejs npm have not achieved, what Phos UPS can do:
- variable level of encapsulation, find examples not possible using JavaScript?  - What practical consequences does this have?

Phoshell Universal Packaging System -- Phups: the Last Mile in Computer Programming

Phos Package Manager PhosPM. Easier to remember like NPM. 

- 1.5
Explain RPML on its own. Generalize from Laravel Blade PHP to other Programming Languages. 



:: - Use - for new section, idea. 
Easier to read. Easy to turn into numbered list or section. 


- Sections
1. TELK

2. Simplify HOW? Phoshell: just list examples to show HOW.
- 2.4 Simplifying React Redux Augmented Reality Programming (Jitsi Meet)

3. Simplify / other consequences? Additional discussions and analysis, with or without code.
- Blindspots
- 3.3 What are the problems we are trying to solve? Consequences

7. Why R3ML?
- 7: 3 problems have been copied to 3.3 / can be ignored

- TELK / Bllindspots
- 3.3 Consequences / 4 Simplifing
  - 4 Simplifying is short term consequences
  - 3.3 contains long term consequences
  - focus on 4. 4 is related to 2. Once 4 is finished, issues related to 3 will be clarified.
  - swap 3 and 4


## 2. Theoretical Foundations of Phoshell


- 2.1 Phoshell definition

Phoshell is derived from the Forth programming language, as we took critical features from Forth and simplify them, to create a highly portable stack machine shell that can be implemented in around 50 lines of JavaScript code or equivalent, that essentially does the following:
- pushes non-function words (tokens) on to the stack;
- executes function words and pushes the results on to the stack.

Phoshell was initially implemented in PHP as an experiment to see how easy it is to implement a simplified stack machine. Eventually, we realized that this simplified stack machine can in fact be implemented in ___any known programming language___ _with the equivalent of around 50 lines of JavaScript or PHP code_, thus making the Forth like script (hence _"Phos"_) a likely candidate to be a ___universal scripting language___.


A stack machine shell maps function tokens in the input, expressed in reverse Polish notation, to native functions of the host programming language. RPN is used to call functions in all the scenarios listed above. As such, ....

Explain with examples of issues in TFJS and ChatMessage etc. Time spent.


The uniqueness of RPN is proven in its ability to encapsulate anything from Python turtle graphics to Jitsi Meet TFJS. The mechanisms behind this are some of the most fundamental principles in programming and mathematics. 

- What do these mean for mortal programmers practically vs. LISPers and computer scientists theoretically?

This is perhaps one of the rare few topics in computer programming that concern the whole spectrum of practical programmers to theoretical computer sientists.



:: convert - bulleted headings to # headings when finished



- Deployable in anything from Python Turtle Graphics, Laravel front-end and back-end to Jitsi Meet Augmented Reality Conferencing, Phoshell is the ultimate programmer's _swiss army knife_.

Inspired by the Forth programming language, Phoshell &mdash; a _stack machine shell_ &mdash; extracts the essential features of Forth, simplifies them, and can be implemented in around 50 lines of JavaScript code or equivalent in _any known programming language_.



### 2.2 History of Stack Machine Systems

- Perhaps the biggest mystery in the short history of computer programming?
  - Have `dc` and Forth programmers ever corssed path?

https://en.wikipedia.org/wiki/Reverse_Polish_notation

Other RP camps? Algol Unilever Burroughs?

HP calculators?

Other RP engineers?

First Unix shell is reverse polish.

https://en.wikipedia.org/wiki/Dc_(computer_program)

Unix claimed the high ground for shell and programming language tools. Forth lost out. Making a comeback.

http://phos.epizy.com/smashlet/?i=1



### 2.3 Phoshell Background and Examples

Phoshell is derived from the Forth programming language, as we took critical features from Forth and simplify them, to create a highly portable stack machine shell that can be implemented in around 50 lines of JavaScript code or equivalent, that essentially does the following:
- pushes non-function words (tokens) on to the stack;
- executes function words and pushes the results on to the stack.

Phoshell was initially implemented in PHP as an experiment to see how easy it is to implement a simplified stack machine. Eventually, we realized that this simplified stack machine can in fact be implemented in ___any known programming language___ _with the equivalent of around 50 lines of JavaScript or PHP code_, thus making the Forth like script (hence _"Phos"_) a likely candidate to be a ___universal scripting language___.

Besides Forth implementations in other programming languages (from C/C++ to Lisp, JavaScript, Java, Rust, Haskell etc.) developed by other programmers, which we too classify as "stack machine shells" (smashlet), we ourselves have implemented Phoshell in:

- C, C++, PHP, Python, Java, JavaScript &mdash; on desktop Linux and Android (Java and NDK)
- Using Laravel Blade PHP, we succeeded in creating a Reverse Polish form of HTML!! &mdash; _a breakthrough perhaps as significant as the invention of HTML itself??_
- An attempt to implement raw Forth within Firefox JavaScript engine as a ___compatible___ alternative to WebAssembly


<img src="https://github.com/udexon/Phoom/blob/master/jitsi_phoshell/jm_chat_icon.png" width=600>

<img src="https://github.com/udexon/Phoom/blob/master/jitsi_phoshell/jm_phoshell.png" width=600>

<hr>




## 2.4 Simplifying React Redux Augmented Reality Programming (Jitsi Meet)

Simplifying React Redux Augmented Reality Programming (Jitsi Meet) using Forth derived Stack Machine Shell
Functionalities of code become more complex. 

1. Can code be made simpler at the same time? 

2. Another misconception: GUI and CLI are unrelated. However GUI is related to graph structure, and therefore Reverse Polish Notation.

3. Compare Smashlet to Redux, both in footprint and architecture. 

Jitsi Meet is field tested, large scale, 100 mb in zip size ... one of the biggest project of any kind, Redux , besides libreoffice. Merge all apps with Phoshell? With all platform module: web, Android, iOS. Active developments, how many commits per week, consistently? 


### 2.5

In the least Phoshell improve documentation and reduce TELK.

- Phoshell is source compatible with the host Programming Language and framework. 

Give examples and explain. 
Examples show:
- Python turtle graphics
- ChatMessage addition
- TFJS




## 3. Blindspots of Programmers 

baby elephant syndrome A term of art for hopeless helplessness learned in childhood, which becomes hard-wired in a person’s psyche as he or she develops and matures.

Segen's Medical Dictionary. © 2012 Farlex, Inc. All rights reserved.


The Baby Elephant Syndrome amongst Programmers
https://see.news/the-chained-elephants-syndrome/


https://medical-dictionary.thefreedictionary.com/baby+elephant+syndrome

baby elephant syndrome A term of art for hopeless helplessness learned in childhood, which becomes hard-wired in a person’s psyche as he or she develops and matures.

Segen's Medical Dictionary. © 2012 Farlex, Inc. All rights reserved.


We do not know what we do not know. When someone tells us something we do not know, half the time we reject it.

- The blindspots by programmers concerns GUI, CLI, stack machine shell, 
- have great consequences, including ....


Phoshell: Overcoming Baby Elephant Syndrome amongst Programmers with a Forth inspired Stack Machine Shell

https://www.thestar.com.my/opinion/columnists/the-star-says/2017/08/13/free-our-young-from-the-baby-elephant-syndrome

The Baby Elephant Syndrome amongst Programmers

https://see.news/the-chained-elephants-syndrome/

https://medical-dictionary.thefreedictionary.com/baby+elephant+syndrome


- 3.1 (use bulleted list for numbering subsection)

Stack machine shell ("smashlet" or "shellet") is such a blind spot amongst programmers. Each and every word in the phrase "stack machine shell" is such fundamental concept that no one will think twice about it. But when chained together, the top Google search result is actually a Reddit post linked to another old repository by this GitHub user (udexon) &mdash; which means we have suceeded in defining this term.

This blind spot amongst programmers is so serious that we may use the Baby Elephant Syndrome or Chained Elephant Syndrome to describe it. It concerns two of the biggest controversies in computer programming:

- Diversification of Programming Languages and Frameworks
- Separation of CLI and GUI


- 3.2 Blindspot: Shell is supposed to simplify things (what things?), but most programmers thought that shell is a huge mysterious beast like Bash which is beyond the reach of common mortals. Thanks to Unix GNU?

Subconcious conditioning, like the little elephant in the circus. Trained not to escape, tied to a pole. When grown up, also not espcaping.


- Another misconception: GUI and CLI are unrelated. However GUI is related to graph structure, and therefore Reverse Polish Notation.



### 3.3 What are the problems we are trying to solve?

#### Consequences
To TLDR the long stories:

- Is it possible to unify all programming languages with a universal script?
- Is it possible to create a CLI shell that can program GUI interactively?



1. The good old learning curve to pick up a new framework / programming language (JavaScript React Redux).

2. Lack of a powerful live debugging system like Forth for new programmers to debug and learn the internal workings of Jitsi.

3. Both reasons above contribute to lack of documentation and manpower to prepare documentation, which lead to a positive feedback in difficulties in getting more developers.

Hence we hope R3ML will overcome these problems, perhaps enable thousands more developers to join our effort &mdash; ___Phoom: an augmented reality conferencing app___. 

The 3 problems mentioned above are not unique to Jitsi. They are perhaps generic to many other free software / open source projects.

https://github.com/udexon/Phoom/blob/master/R3ML_Jitsi_Phoom.md

We illustrate how stack machine shell resolves these issues by using Jitsi-Meet as example.


- 3.4 Phoshell projects as large scale software engineering projects
  - How many people? How long will it take to start contributing to Jitsi-Meet or similar projects?

Consider N the number of programmers who have one hour free time every day. They could have write something to create AR Conferencing app. But due to time required to learn entry level knowledge (TELK), this number is greatly reduced. If we reduce TELK, then N increases.


====

:: add number for psragraph first. can start using number as refernce to reorganize texts before deciding section subjects.






## 7. Why R3ML?

As decribed in the following GitHub issue:

- https://github.com/jitsi/jitsi-meet/issues/5269#issuecomment-622661995

- TLDR: The Tensor Flow (TFJS) Body Pix algorithm is already included in Jitsi-Meet.

As such, we may ask:

- Why hasn't anyone use TFJS Body Pix to extract the human body as avatar, to be used in an Augmented Reality conferencing app?

We suspect there are three primary reasons:

1. The good old learning curve to pick up a new framework / programming language (JavaScript React Redux).

2. Lack of a powerful live debugging system like Forth for new programmers to debug and learn the internal workings of Jitsi.

3. Both reasons above contribute to lack of documentation and manpower to prepare documentation, which lead to a positive feedback in difficulties in getting more developers.

Hence we hope R3ML will overcome these problems, perhaps enable thousands more developers to join our effort &mdash; ___Phoom: an augmented reality conferencing app___. 

The 3 problems mentioned above are not unique to Jitsi. They are perhaps generic to many other free software / open source projects.

- Why do we need that many developers for AR conferencing?

__We believe this is the beginning of a new era of computing:__

- _If the 2010 decade is defined by iPhone and Android mobile devices, then_ ___2020s should be the era of Virtual Reality &mdash; 3D VR AR___, _with opreating systems and devices that transcend the old, but the programming language has to be_ ___powerful___ _like Forth and yet_ ___easy to learn___ _like the Turtle graphics Logo programming language._

Hence ___Phoom R3ML___.

- Footnote: in figures 1 and 2, the camera is actually pointing at the monitor showing the browser console. _Can the program understand what it is seeing?_ We hope this will be a small step towards _Star Trek_ or _Star Wars_ &mdash; where Reverse Polish Notation opens up _homoiconic metaprogramming_, very likely the last mile towards achieving human level artificial intelligence. _But then that belongs to another article at another time._



The 3 problems mentioned above are not unique to Jitsi. They are perhaps generic to many other free software / open source projects.

- Why do we need that many developers for AR conferencing?

__We believe this is the beginning of a new era of computing:__

- _If the 2010 decade is defined by iPhone and Android mobile devices, then_ ___2020s should be the era of Virtual Reality &mdash; 3D VR AR___, _with opreating systems and devices that transcend the old, but the programming language has to be_ ___powerful___ _like Forth and yet_ ___easy to learn___ _like the Turtle graphics Logo programming language._


10. Tentative Titles

Phoshell:  Extremely Lightweight "Super IDE" with Run-time Editing and Debugging

Phoshell: A Universal, Extremely Lightweight "Embedded IDE" with Run-time Editing and Debugging Functionalities

Jitsi Phoshell:  Extremely Lightweight "Super IDE" From Python Turtle Graphics to Jitsi Meet Augmented Reality Conferencing


Shell + GUI = IDE


Phoshell: Overcoming Baby Elephant Syndrome amongst Programmers with a Forth inspired Stack Machine Shell




