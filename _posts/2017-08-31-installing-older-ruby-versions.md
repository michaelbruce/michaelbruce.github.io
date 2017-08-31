---
layout: default
title: Installing older ruby versions
---

If you use ruby-install to install versions of ruby you may have noticed some
will fail to compile, I came across this recently, requiring 2.3.0 for a
project.

Ruby 2.3.0 won't compile with the latest version of openssl or gcc on Arch Linux
(1.1.0f & 7 at time time of writing)

The solution is to pass extra flags to use gcc 5 and openssl 1

`CC=/usr/bin/gcc-5 PKG_CONFIG_PATH=/usr/lib/openssl-1.0/pkgconfig ruby-install ruby 2.3.0`

