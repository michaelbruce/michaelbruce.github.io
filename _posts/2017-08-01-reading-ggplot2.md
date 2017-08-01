---
layout: default
title: Reading Hadley's ggplot2
---

## Reading Hadley's ggplot2

![ggplot2]({{ site.baseurl }}/public/ggplot2.png){: .center-image }

Following DHH's advice in his 2014 railsconf talk I will be reading code in an
effort to improve my own. I have chosen to review ggplot2 as I don't know what
good R code looks like.

### Project Organisation

The codebase layout is fairly usual with R code in an R folder, testing using
the testthat package under the tests folder. There are 173 R files with no
subdirectories, instead this large list of files is broken down with high level
keywords at the beginning of each filename such as geom-error.R,
geom-freqpoly.R.

Two files that don't follow this convention are zzz & zxx and piqued my
interest. zzz has function definitions that aren't called in the codebase. Their
names suggest that they are related to releasing and loading the package so
perhaps they are used by a packaging mechanism that I am not aware of. zxx has a
series of aliases to function definition such as British to American spellings
of colour.

### Specific Classes

There doesn't appear to be a limit to the number of lines for each R file here,
ranging from 7 to over 600. A stark constrast to the 100-line classes rule of
thumb picked up from Sandi Metz. Taking the largest file, scale-.r at 664 lines
was quite surprising! The Scale function is created from a ggproto function and
uses functions as arguments, Hadley has been quite liberal with frequent use of
commentary throughout. Beyond that I found it hard to reason what was going on,
ggproto came up a few times maybe I'd have better luck there. Opening the file I
find that ggproto is inspired by a similar proto package. It's refreshing for me
as a reader to learn some of the initial reasoning by Hadley over his approach
here, in his own words:

> *In most cases, creating a new OO system to be used by a single package is
> not a good idea. However, it was the least-bad solution for ggplot2 because
> it required the fewest changes to an already complex code base.*

Generally I am getting a sense that rather than breaking down the package into
atomic parts, Hadley elects to use documentation including invocation examples
to help a user understand how to make use of the package.

plot.R appears to be the starting point for the package, where a new ggplot is
made. Inside the ggplot method is the line `UseMethod("ggplot")`, which is
confusing since I haven't come across UseMethod before. Going on my experience
with ggplot my guess is that this line is executing other functions that are
added to it in the typical fashion.

```ggplot() + geom_point(data = df, aes(gp, y))```

The R Pipe `%>%` is not used in the R folder at all.
