# SPL, the Shakespeare Programming Language

----

## About this Repository

_**NOTE: This is a mirror of the original project, only available as tarballs
from SourceForge.**_

It also includes copies of:
  - [HTML Documentation](https://krayon.github.io/shakespearelang/docs/shakespeare.html)
  - [PDF Documentation](https://krayon.github.io/shakespearelang/docs/shakespeare.pdf)

As well as some minor fixes:
  - Fix fibonacci compile warning
  - Fix "sqrt()" compile error
  - Fix "multiple definition" compile error
  - Remove duplicate "rotten"

## Summary

SPL is an esoteric programming language, designed and implemented by Jon Åslund
and Karl Wiberg. Every SPL program looks like a Shakespeare play. It’s a real
programming language, easily capable of simulating a Turing machine. They expect
it to overtake C++ in popularity any day now.

## Links

- [Wikipedia entry](https://en.wikipedia.org/wiki/Shakespeare_Programming_Language)
- [Sourceforge Website](http://shakespearelang.sourceforge.net/)
  - [HTML Documentation](http://shakespearelang.sf.net/report/shakespeare/)
  - [PDF Documentation](http://shakespearelang.sf.net/report/shakespeare.pdf)
- [Karl Wiberg's SPL page](https://treskal.com/kha/spl)

## Potential future enhancements

### Initialise variables

Instead of having to initialise a value in a scene:

```
Romeo, a man who loves a woman.
Juliet, a woman who loves a man.

Act I: It Begins.
Scene I: Wednesday morning.

[Enter Romeo and Juliet]

Juliet:
    You are as big as the difference between a Lord and a flower.
```

Simply:

```
Romeo, a man who loves a woman, as big as the difference between a Lord and a
flower.
```

### Jump to Act/Scene names

Instead of having to name an Act or Scene:

```
Act I: The Beginning.
Scene I: Wednesday morning.

...

Scene II: The kitchen table.

Juliet:
    You are as good as the sum of thyself and a flower.

Romeo:
    Am I better than a fine sunny summer's day?
    If not, let us return to Scene II.

Romeo:
    Am I better than you?

Juliet:
    If so, we shall proceed to Scene III.

Romeo:
    Let us return to Scene II.

Scene III: The bedroom.

```

We should be able to use the act/scene names:

```
Act I: The Beginning.
Scene I: Wednesday morning.

...

Scene II: The kitchen table.

Juliet:
    You are as good as the sum of thyself and a flower.

Romeo:
    Am I better than a fine sunny summer's day?
    If not, let us return to the kitchen table.

Romeo:
    Am I better than you?

Juliet:
    If so, we shall proceed to the bedroom.

Romeo:
    Let us return to the kitchen table.

Scene III: The bedroom.

...
```

### Ignored actions/comments

Actions or comments would be a welcome addition.

Maybe any line starting with `*`:

```
Romeo:
    Am I better than you?

* Romeo winks at Juliet.

Juliet:
    If so, we shall proceed to the bedroom.
```

Or dialog that is intentially missing the `:`:

```
Romeo:
    Am I better than you?

Romeo winks at Juliet.

Juliet:
    If so, we shall proceed to the bedroom.
```

### More flexability with stage entry/exits

Currently only literal Enter/Exits supported:

```
[Enter Romeo]
...
[Enter Juliet]
...
[Exit Romeo and Juliet]
```

It would be good to have more flexibility:

```
[Enter Romeo]
...
[Enter Juliet above at a window]
...
[Exit Romeo carrying a potato]
[Exit Juliet on a Segway]
```

### Support ignoring unrecognised text

Whilst they may serve no purpose, additional lines that could be ignored if not
recognised, could make the "code" more pleasurable to read. Where:

```
But soft! What light through yonder window breaks?
It is the East, and Juliet is the sun!
Arise, fair sun, and kill the envious moon.
Be not her maid, since she is envious.
Her vestal livery is but sick and green,
And none but fools do wear it. Cast it off.
Thou art as sweet as a blossoming golden flower.
Would through the airy region stream so bright
That birds would sing and think it were not night.
See how she leans her cheek upon her hand!
O that I were a glove upon that hand,
That I might touch that cheek!
```

Would be processed as:

```
Thou art as sweet as a blossoming golden flower.
```

----
[//]: # ( vim: set ts=4 sw=4 et cindent tw=80 ai si syn=markdown ft=markdown: )
