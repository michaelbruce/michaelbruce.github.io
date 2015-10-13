---
layout: default
title: Quartermaster
---

# Quartermaster

When working on a collection of repositories, it's useful to gain a high level view of what's going on.

Here's a tool that does just that. It reads a list of paths from csv and outputs formatted results for each entry.

![Quartermaster]({{ site.baseurl }}/public/quartermaster.png){: .center-image }

#### The output for each project can be one of 4 states

- \[Red, project is missing locally\]
{: style="color: #E5002E; font-style: bold;" }

- Green is for no changes
{: style="color: #88D400; font-style: bold;" }

- Pink - Uncommitted changes
{: style="color: #F3074C; font-style: bold;" }

- Blue - Ahead of origin/branch
{: style="color: #4EBFEA; font-style: bold;" }

It makes checking that code has been checked in easier! See it [here on github.](https://www.github.com/michaelbruce)

Michael Bruce
{: .signature }
