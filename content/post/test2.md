---
title: "Test post"
author: "Ajay Mehta"
date: '2020-05-03'
description: Template for Rmarkdown
draft: yes
categories: ["R", "testing"]
tags: []
slug: test-rmd
compact-title: no
hljs: true
params:
  theme: ""
output:
  html_page:
    keep_md: false
editor_options:
  markdown:
    doctype: blogdown    
---

This is a R Markdown template for a blog post.

<!-- https://gohugo.io/content-management/summaries/ -->
<!--more-->

# Section heading in sentence case

Citation of a website[^1].

## Subsection heading

A plot:

``` r
plot(1:10)
```

<img src="/post/test2_files/figure-html/my-plot-1.svg" width="576" />

Code chunk:

``` r
library(tidyverse)
rnorm(10) %>% sum()
```

``` bg-success
## [1] -2.041044
```

This is a test: `\(\overset{f(a)}{a \in \mathbb{R}}\)`

<pre><code class='language-r'><code>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1<br>a <span style="background-color:#ffff7f"><-</span> 1</code></code></pre>

`$$\begin{align} y_t & = l_{t-1} + \phi{b_{t-1}} + \epsilon_t \\ l_t & = l_{t-1} + \phi{b_{t-1}} + \alpha\epsilon_t \\ b_t & = \phi{b_{t-1}} + \beta\epsilon_t \end{align}$$`

[^1]: Hugo static site generator. <https://gohugo.io/>
