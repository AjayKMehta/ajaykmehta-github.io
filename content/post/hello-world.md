---
title: "Hello 🌍"
slug: "hello-world"
author: "Ajay Mehta"
draft: true
date: 2020-01-08T20:31:04-08:00
---


# Header

This is a test[^1].

## Haskell

```haskell
m >>= f

foldl :: (a -> b -> a) -> a -> [b] -> a
foldl _ z [] = z
foldl f z (x:xs) = foldl f (f z x) xs
```

## C#

```csharp
var x = new List<string>();
```

## Python

```python
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
Get-Module -ListAvailable | group Name | ? Count -gt 1
```

## Math

$$\alpha = \frac{1}{3}$$

## Emoji

:smile:

## Shortcodes

### Built-in

{{< youtube w7Ft2ymGmfc >}}

### Custom

The year `{{`**`< year >`**`}}` is `{{< year >}}`.

[^1]: Footnotes work.
