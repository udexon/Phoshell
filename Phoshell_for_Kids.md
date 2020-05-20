
# Phoshell for Kids

The name Phoshell is perhaps yet another evolving term, conceived to describe a simple yet complicated module, embeddable in any program, any programming language and any operting system, that is perhaps the most significant breakthrough in computing technology since the invention of the World Wide Web, iPhone and Android.

As such, describing Phoshell to ordinary users today could be like explaining WWW to men in the street before it was invented, similarly with iPhone and Android. 

Perhaps the best place to start when illustrating Phoshell is the Turtle Academy website, an educational website to demonstrate the LOGO programming language for drawing simple to complex shapes on a web page:

https://turtleacademy.com/

https://github.com/udexon/Homoiconism/blob/master/Q21_Compare_Logo.md

Perhaps the take away lessons from Turtle Academy are:

- anyone can learn to program with a simple programming language
- a simple programming language like LOGO can draw simple to complex shapes

These simple principles have been lost in recent years as more complex programming languages become mainstream, with perhaps Python being regarded as "the simplest" of them all.

Incidentally, a turtle graphics library has been ported to Python:

https://opentechschool.github.io/python-beginners/en/simple_drawing.html

We shall demonstrate that how a Phoshell written in Python can extend the functionalities of turtle graphics into something more ambitious, while keeping the programming language to be no more complicated than Microsoft Excel.

So this will be is one of the first few simple steps in our journey .... to ultimately unify programming and mathematics with Phoshell.

https://github.com/udexon/Metashellet/blob/master/turtle1.py

<img src="https://github.com/udexon/Metashellet/blob/master/Turtle_SM.png" width=600>

The path shown in the diagram above is drawn using the Reverse Polish Notation expression as shown below, where `f` is mapped to `forward()` and `l` is mapped to `left()`:

```Python
SM("25 f 45 l 50 f 45 l 50 f")
```

We intentionally leave the `SM()` (Stack Machine) function to be in a barebone state, as more complete stack machine (metashellet) module can be found in the examples above (PHP, JavaScript, Java).

