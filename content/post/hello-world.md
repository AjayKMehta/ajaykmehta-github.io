---
title: "Hello 🌍"
slug: "hello-world"
author: "Ajay Mehta"
draft: true
date: 2020-01-08T20:31:04-08:00
---

This post is to test various features of Hugo.

<!--more-->

# Header

This is a test[^1].

## Haskell

{{< highlight haskell "linenos=table, hl_lines=1 3-4" >}}
m >>= f

foldl :: (a -> b -> a) -> a -> [b] -> a
foldl _ z [] = z
foldl f z (x:xs) = foldl f (f z x) xs
{{< /highlight >}}

## C\#

```csharp
var x = new List<string>();
```

## Python

```python {linenos=table, hl_lines=["1-2", 4]}
import numpy as np
import pandas as pd

[x^2 for x in range(10)]
```

## R

```r
iris %>%
group_by(Species) %>%
summarize(
    avg_length = mean(Sepal.Length),
    max_length = max(Sepal.Length)
)
```

## PowerShell

```powershell
Get-Module -ListAvailable |
    group Name |
    ? Count -gt 1
```

## Math

`\tag{1}`  does not work.

$$\alpha = \frac{1}{3}$$

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

### Github-flavored Markdown

<kbd>W</kbd>

```diff
10 PRINT "BASIC IS COOL"
- 20 GOTO 11
+ 20 GOTO 10
```

[^1]: Footnotes work.
