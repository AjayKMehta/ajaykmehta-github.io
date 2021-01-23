---
title: '{{ replace .Name "-" " " | title }}'
slug: '{{ .Name }}'
date: '{{now.Format "2006-01-02"}}'
author: "Ajay Mehta"
description:
summary:
draft: true
categories: ["R"]
tags: []
compact-title: no
output:
  html_document:
    keep_md: true
editor_options:
  markdown:
    doctype: hugo
---

This is a special RMarkdown (.Rmd) template for a blog post used in a page bundle with support for Hugo features.

**Add summary here or remove line below.**
<!--more-->

```{r setup, include=FALSE}
options(warnPartialMatchArgs = FALSE, warnPartialMatchDollar = FALSE)

knitr::opts_chunk$set(
  class.output = "bg-success",
  class.message = "bg-info text-info",
  class.warning = "bg-warning text-warning",
  class.error = "bg-danger text-danger"
)

# https://ropensci.org/technotes/2020/04/23/rmd-learnings

# Options to have images saved in the post folder
# And to disable symbols before output
knitr::opts_chunk$set(fig.path = "", comment = "")

# knitr hook to make images output use Hugo options
knitr::knit_hooks$set(
  plot = function(x, options) {
    hugoopts <- options$hugoopts
    paste0(
      "{{<figure src=",
      '"', x, '" ',
      if (!is.null(hugoopts)) {
        glue::glue_collapse(
          glue::glue('{names(hugoopts)}="{hugoopts}"'),
          sep = " "
        )
      },
      ">}}\n"
    )
  }
)

# knitr hook to use Hugo highlighting options
knitr::knit_hooks$set(
  source = function(x, options) {
  hlopts <- options$hlopts
    paste0(
      "```r ",
      if (!is.null(hlopts)) {
      paste0("{",
        glue::glue_collapse(
          glue::glue('{names(hlopts)}={hlopts}'),
          sep = ","
        ), "}"
        )
      },
      "\n", glue::glue_collapse(x, sep = "\n"), "\n```\n"
    )
  }
)

# https://bookdown.org/yihui/rmarkdown-cookbook/font-color.html
colorize <- function(x, color) {
  if (knitr::is_latex_output()) {
    sprintf("\\textcolor{%s}{%s}", color, x)
  } else if (knitr::is_html_output()) {
    sprintf("<span style='color: %s;'>%s</span>", color,
      x)
  } else x
}

# https://bookdown.org/yihui/rmarkdown-cookbook/hook-truncate.html
# Use out.lines chunk option to truncate output.

# save the built-in output hook
hook_output <- knitr::knit_hooks$get("output")

# set a new output hook to truncate text output
knitr::knit_hooks$set(output = function(x, options) {
  if (!is.null(n <- options$out.lines)) {
    x <- xfun::split_lines(x)
    if (length(x) > n) {
      # truncate the output
      x <- c(head(x, n), "....\n")
    }
    x <- paste(x, collapse = "\n")
  }
  hook_output(x, options)
})
```

## Shortcodes

Shortcodes in the Rmd file need to be between `<!--html_preserve-->` and
`<!--/html_preserve-->`.

<!--html_preserve-->
{{< figure src = "name-of-image.png" width = "400" alt = "this is the alternative text" >}}
<!--/html_preserve-->

Once this file is knitted the plot below will be inserted with the correct syntax:

```{r plot, hugoopts=list(alt="alternative text please make it informative", caption="This is what this image shows, write it here or in the paragraph after the image as you prefer.", width=300)}
plot(1:10)
```

**Embed a tweet** by using a Hugo shortcode:

<!--html_preserve-->
{{< tweet 1138216112808529920 >}}
<!--/html_preserve-->

## [Code highlighting](https://gohugo.io/content-management/syntax-highlighting/#highlight-shortcode)

```{r ggplot, message=FALSE, hlopts = list(linenos='table',hl_lines='[1, 4]')}
library(tidyverse)

ggplot(iris, aes(x = Sepal.Length, y = Petal.Length, color = Species)) +
  geom_point()
```
