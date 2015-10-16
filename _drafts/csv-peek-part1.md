---
layout: default
title: CSV Peek Pt 1
---

# CSV Peek

_This is the first in a series on the development of a CSV viewer, written in ruby._

![csvpeek]({{ site.baseurl }}/public/csvpeek.png){: .center-image }

This is CSV Peek, my first fullscreen terminal application. To print over the entire screen I learnt how the cursor position is moved using escape sequences much like when you use Ctrl + C to shutdown an application. They're known as VT100 codes and if you'd like to find out more about this I'd suggest
[Random Access Terminal](http://graysoftinc.com/terminal-tricks/random-access-terminal), an article by James Edward Gray.

The program doesn't use any external gems and runs as a single script. The shbang calls bash that then calls ruby, allowing arguments to be passed in under linux.

    #!/usr/bin/env bash
    exec /usr/bin/env ruby --disable-gems -x "$0" $*
    #!ruby

I've been using this task to practice the idea of creating a functional core, built from methods that have a single purpose or as few side effects as possible. The IO handling in UserInput 

[include here in code scrollbox? github applet?]

It's been interesting so far, hitting walls that are usually invisible. Things like handling resizing of the terminal.
At this point there are a lot more that needs to be done before it's polished and ready to be used (bye excel!)

[further, integration to vim w/ tmux, opening .csv from gf overides and opens csvpeek in a new tmux frame]
[influence from vim - include cmdline sql-esque calls e.g :SELECT Name,Phone from %]

[using commit f98e0b4]

