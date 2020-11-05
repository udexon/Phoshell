# Phoshell

1. Bash script &mdash; the script language which programmers love to hate.

It is indispensable, yet impossible to remember.

2. `ffmpeg` &mdash; perhaps the most powerful and yet useful tool especially in today's world dominated by every growing social media; another tool that programmers love to hate, infamous for its complicated and yet necessary parameters for editing audio and video.

3. Phoshell &mdash; a very thin Bash wrapper based on Phoscript, a simplified metaprogramming script derived from the Forth programming language, based on Reverse Polish Notation.

## A. Examples

1. Addition and Stack
<img src="https://github.com/udexon/Phoshell/blob/master/Phoshell/img/add_55_22.png" width=200>

```
> ./sm 55 22 + f_s
1: 77 
```
`./sm`: `sm` is the abbreviation for stack machine. We choose this name because it is short and generic.

`55 22 +`: `55 + 22` in Reverse Polish Notation. The result is pushed on to the stack.

`f_s`: displays the stack.

`1: 77`: `1:` the length of the stack. `77` is the result.


2. The simplest task in making a presentation video consists of the following:

- a. Create a slide. Make a screenshot. Convert the screenshot into a video clip with voice over.
- b. Record the audio using mobile phone or other deivces.
- c. Merge the audio and video stream into one mp4 file.
- d. Reencode the mp4 to the resolution required to eliminate inconsistencies create in the previous steps.
