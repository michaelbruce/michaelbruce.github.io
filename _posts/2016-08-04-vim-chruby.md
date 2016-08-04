---
layout: default
title: vim-chruby
---

# vim-chruby

When writing projects in ruby it's necessary to be using the correct ruby version.

The version manager I've been using is chruby and it serves it's purpose very well. One problem that I've had for a while is switching ruby versions in a vim instance since it has already taken environment variables from the shell that spawned it. At this point the chruby command can't change the PATH variable used in vim.

vim-chruby solves this problem by manipulating the PATH variable inside vim in the same way. It has version number completion too. Tpope's vim-rvm helped me a lot in writing this.

You can check it out [here on github.](https://www.github.com/michaelbruce/vim-chruby)
