---
layout: default
title: CSV Peek Pt 1
---

# CSV Peek

This is the first in an ongoing series about the development of a command line based CSV viewer, written in ruby.

![csvpeek]({{ site.baseurl }}/public/csvpeek.png){: .center-image }

It's the first fullscreen terminal application, to do this I learn about VT100 codes and how they're used to do things like moving the cursor around the screen.
Gary Bernhardt (link here) and James Edward Grey (link here)

[include here in code scrollbox? github applet?]

It's been interesting so far, hitting walls that are usually invisible. Things like handling resizing of the terminal.
At this point there are a lot more that needs to be done before it's polished and ready to be used (bye excel!)

[further, integration to vim w/ tmux, opening .csv from gf overides and opens csvpeek in a new tmux frame]
[influence from vim - include cmdline sql-esque calls e.g :SELECT Name,Phone from %]

[using commit f98e0b4]

