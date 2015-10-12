---
layout: default
title: Quartermaster
---

# Quartermaster

When working on a collection of repositories, it's useful to gain a high level view of what's going on.

Here's a tool that does just that. It reads a list of paths from csv and outputs formatted results for each entry.

![Quartermaster]({{ site.baseurl }}/public/quartermaster.png){: .center-image }

#### The output for each project can be one of 4 states

\[Red - Project is missing locally\]
{: style="color: #E5002E; font-style: bold;" }

Green - No changes
{: style="color: #88D400; font-style: bold;" }

Pink - Uncommitted changes
{: style="color: #F3074C; font-style: bold;" }

Blue - Ahead of origin/branch
{: style="color: #4EBFEA; font-style: bold;" }

Names in red, circled in square brackets let us know that the project was not found locally.
Present repositories without changes are shown in green.
(what does each one of 3 do)
(4 do - new, blue when commit made but not pushed back to origin, BillsBuddy was in this state?)

Note this does not fetch/modify git state, I find it's most useful when making sure that all my code has been 

The script totals 200 LOC.

Michael Bruce
{: .signature }
