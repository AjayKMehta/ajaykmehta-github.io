---
title: "Hello 🌍"
slug: "hello-world"
author: "Ajay Mehta"
draft: true
date: 2020-01-08T20:31:04-08:00
categories: ["testing"]
tags: []
# https://gohugo.io/content-management/urls/#aliases
aliases:
    - /posts/hello-world/
---

This post is to test various features of Hugo.

<!--more-->

## Syntax highlighting

This is a test[^1].

### Haskell

<!-- <https://gohugo.io/content-management/syntax-highlighting/#highlight-shortcode> -->
{{< highlight haskell "linenos=table, hl_lines=1 3-4" >}}
m >>= f

foldl :: (a -> b -> a) -> a -> [b] -> a
foldl _ z [] = z
foldl f z (x:xs) = foldl f (f z x) xs
{{< /highlight >}}

### C\#

```csharp
var x = new List<string>();
```

### Python

```python {linenos=table, hl_lines=["1-2", 4]}
import numpy as np
import pandas as pd

[x^2 for x in range(10)]
```

### R

```r {linenos=table, hl_lines=[1, 3]}
iris %>%
group_by(Species) %>%
summarize(
    avg_length = mean(Sepal.Length),
    max_length = max(Sepal.Length)
)
```

### PowerShell

```powershell
Get-Module -ListAvailable |
    group Name |
    ? Count -gt 1
```

## Math

> :bulb: **Prefix `$$` with `` ` ``.**

`\tag{1}`  does not work unless you do this:

```text
$$\tag{1}\alpha = \frac{1}{3}$$
```

`$$\tag{1}\alpha = \frac{1}{3}$$`

`$$\begin{align}
B := \left\{\frac{\bar{y}_i-\bar{y}_j}{\underline{x}_i-\underline{x}_j}:(i,j) \in D^2\ and\ \underline{x}_i \gt \underline{x}_j\ and\ \bar{y}_i \gt \bar{y}_j\right\} \cup \\
\left\{\frac{\underline{y}_i-\underline{y}_j}{\underline{x}_i-\underline{x}_j}:(i,j) \in D^2\ and\ \underline{x}_i \gt \underline{x}_j\ and\ \underline{y}_i \lt \underline{y}_j\right\} \cup \\
\left\{\frac{\bar{y}_i-\bar{y}_j}{\bar{x}_i-\bar{x}_j}:(i,j) \in D^2\ and\ \bar{x}_i \gt \bar{x}_j\ and\ \bar{y}_i \lt \bar{y}_j\right\} \cup \\
\left\{\frac{\underline{y}_i-\underline{y}_j}{\bar{x}_i-\bar{x}_j}:(i,j) \in D^2\ and\ \bar{x}_i \gt \bar{x}_j\ and\ \underline{y}_i \gt \underline{y}_j\right\} \cup \{0\}
\end{align}$$`

## Emoji

:smile:

## Shortcodes

### Built-in

{{< youtube w7Ft2ymGmfc >}}

### Beautiful Hugo

There are two extra shortcodes provided (along with the customized figure shortcode).

#### Details

This simply adds the html5 detail attribute, supported on all *modern* browsers. Use it like this:

{{% details "This is the details title (click to expand)" %}}
This is the content (**hidden until clicked**).
{{% /details %}}

#### Split

This adds a two column side-by-side environment (will turn into 1 col for narrow devices):

{{< columns >}}
This is column 1.
{{< column >}}
This is column 2.
{{< endcolumns >}}

### Custom

The year `{{`**`< year >`**`}}` is `{{< year >}}`.

## GitHub-flavored Markdown

<kbd>W</kbd>

```diff
10 PRINT "BASIC IS COOL"
- 20 GOTO 11
+ 20 GOTO 10
```

[^1]: Footnotes work.

## Markdown attributes {.text-serif #a-heading title="Hovered"}

Hugo 0.81 introduced attribute lists on markdown blocks like lists, tables etc in which the element's attributes would be defined in curly braces.

## Mermaid

{{<mermaid align="left">}}
graph LR;
A[Hard edge] -->|Link text| B(Round edge)
B --> C{Decision}
C -->|One| D[Result one]
C -->|Two| E[Result two]
{{< /mermaid >}}

Git graph doesn't render:

{{<mermaid>}}
gitGraph
    commit id: "3aa7786"
    branch origin/main
    commit id: "ec38060 Address linter warnings."
    commit id: "3ff098e Add packages."
    checkout main
    commit id: "12301"
    merge origin/main
{{</mermaid>}}
