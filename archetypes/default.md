---
title: '{{ .Name | replaceRE "-" " " | title }}'
slug: '{{ .Name }}'
date: '{{now.Format "2006-01-02"}}'
author: "Ajay Mehta"
description:
summary: "Enter summary here or use text before <!--more-->."
draft: true
categories: []
tags: []
---

This is the Markdown (.md) template for a blog post.
To generate your post with R Markdown (.Rmd), use that template instead.

**Add summary here or remove line below.**
<!--more-->
