# Phoshell

1. Bash script &mdash; the script language which programmers love to hate.

It is indispensable, yet impossible to remember.

2. `ffmpeg` &mdash; perhaps the most powerful and yet useful tool especially in today's world dominated by every growing social media; another tool that programmers love to hate, infamous for its complicated and yet necessary parameters for editing audio and video.

3. Phoshell &mdash; a very thin Bash wrapper based on Phoscript, a simplified metaprogramming script derived from the Forth programming language, based on Reverse Polish Notation.

The core of Phoshell script `sm` (abbreviation for "stack machine", chosen as we want a two letter short name and for being generic), and Phoscript implementations in other programming languages, consists of the following steps:

- i. split a space delimited string into tokens or "words" in Forth or Phoscript terminology.
- ii. loop through the list of words (tokens):
  - execute (evaluate) the current word if it is a function word
  - push the current word on to the stack if it is a non-function word

The full source code of `sm` is given here:
- https://github.com/udexon/Phoshell/blob/master/Phoshell/sm

In fact, the above is the generic design of any stack machine and can be found in the interpreter in any programming languages.

This mechanism is so simple that it is unfortunate that it has not been more widely publicized. It so therefore one of the aims of this project to promote it so that Phoscript, or any Reverse Polish Notation based programming language, can become a ___universal metaprogramming script___ to interface to any host programming language, thereby _solving the problem of diminishing returns due to growing complexities of programming langauges._

```bash
args=("$@")
S=()

# TODO: change i to longer var name to avoid global var conflict ??
for ((i=0; i < $#; i++))
{
    isFunction ${args[$i]}
    if [ $? -eq 0 ]; then
        # echo 'Function exists!'
        # E=eval "${args[$i]}"
        eval "${args[$i]}"
        # `eval ${args[$i]}`
        # echo $E
        # $($E)
    elif alias ${args[$i]} 2>/dev/null >/dev/null; then 
        echo ${args[$i]} is alias
        eval "${args[$i]}"
    elif [ "${args[$i]}" = "+" ]; then
        # echo "is plus"
        add:
    else
        # echo 'Function does not exist...'
        S+=("${args[$i]}")    
    fi
}

```
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

<hr>

2. 

- The simplest task in making a presentation video consists of the following:
  - a. Create a slide. Make a screenshot. Convert the screenshot into a video clip with voice over. The `ffmpeg` commands to accomplish this are:
  ```
  # get length of audio file
  ffprobe -i $a -show_entries format=duration -v quiet -of csv="p=0"   
  
  # create a silent mp4 from png
  ffmpeg -loop 1 -i $i -c:v libx264 -vf "pad=ceil(iw/2)*2:ceil(ih/2)*2 -t $t -pix_fmt yuv420p $o
  ```
  - b. Record the audio using mobile phone or other deivces.
  - c. Merge the audio and video stream into one mp4 file.
  ```
  ffmpeg -i $i1 -i $i2 -c:v copy -c:a aac $o
  ```
  - d. Reencode the mp4 to the resolution required to eliminate inconsistencies create in the previous steps.
  ```
  ffmpeg -i $i1 -c:a aac -vcodec libx264 -s 1920x1080 -r 60 -strict experimental $o
  ```

As you can see the complexities of the `ffmpeg` parameters involved would turn off the most seasoned programmers. With Phoshell, we have turned the above to something like the following:

- a. Get audio duration and make mp4 from png:
```
> ./sm t.m4a f_duration dup: GEISHA/img/GEISHA.png o_1.mp4 f_p2m
```
- c. Merge the audio and video stream into one mp4 file.
```
> ./sm t.m4a o_1.mp4 o_1x.mp4 f_mav
```
- d. Reencode the mp4 to the resolution required to eliminate inconsistencies created in the previous steps.
```
> ./sm o_1x.mp4 o_1r.mp4 f_renc
```

### Explanations

Phoshell simplifies both `bash` and `ffmpeg` commands and parameters via the following mechanism:

1. hiding details

2. renaming or alias of functions with something easier to remember. This can be done arbitrarily according to the choice of programmers as well as using native langauge (national language) with Unicode. e.g. more than one aliases can point to the same function.

To illustrate, for the step to obtain the duratoin of the audio file, the original command is:
```
  # get length of audio file
  ffprobe -i $a -show_entries format=duration -v quiet -of csv="p=0"   
```

The corresponding Phoscript command is:
```
> ./sm t.m4a f_duration
```

The Phoscript function `f_duration` is defined as (hiding details):
```bash
function f_duration
{
    a="`f_end`"; f_pop;
    echo $a
    b="ffprobe -i $a -show_entries format=duration -v quiet -of csv="
    c='"p=0"'
    echo $b$c
    # echo `eval $b$c`
    S+=(`eval $b$c`)
}
```

Further, `f_duration` can be aliased as `dur:`:
```
alias dur:=f_duration
```

- a. Get audio duration and make mp4 from png:
```
> ./sm t.m4a f_duration dup: GEISHA/img/GEISHA.png o_1.mp4 f_p2m
```

`t.m4a`: input audio file
`f_duration`: function to determine duration of input audio

```
function f_duration
{
    a="`f_end`"; f_pop;
    echo $a
    b="ffprobe -i $a -show_entries format=duration -v quiet -of csv="
    c='"p=0"'
    echo $b$c
    # echo `eval $b$c`
    S+=(`eval $b$c`)
}
```
`a="``f_end``"` reads the "top of stack" (TOS) item. `f_pop` pops TOS.

String `a` is then inserted into string `b` along with the command `ffprobe` and its parameters.

`eval $b$c` executes the string `$b$c`. 

`S+=(...)` pushes the result (duration of audio file) to the stack `S`. 

`dup:` duplicates audio length (now at TOS) and pushes it on to the stack.

`GEISHA/img/GEISHA.png`: input file slide screenshot 

`o_1.mp4`: output file silent mp4

`f_p2m`: converts input `png` to silent `mp4`

We adopt 2 naming conventions for Phoscript functions: `f_*` prefix or `:` suffix, e.g. `dur:`. This is to improve readability, i.e. to distinguish function words (tokens) from non-function words. These conventions do not exist in traditional Forth.

Step (c) (merge audio and video) is performed by `f_mav` &mdash; we have chosen a function name that is easy to remember

Step (d) (reencode video file) is performed by `f_renc`.

The definitions of these functions are listed in `sm`:

https://github.com/udexon/Phoshell/blob/master/Phoshell/sm

Programmers just need to keep the main loop of `sm` at the end. Additional functions and aliases can be defined independently to extend the functionalities of `sm`.

<!--
In practice, step (b) is done first, as we need to get the duration of the audio to create a silent mp4 of the same length in (a).
  - The code to accomplish this is at line 130 `function f_duration` in `sm`.
--> 

- Sanwich API
