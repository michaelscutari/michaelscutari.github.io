---
title: "Markdown Demo"
date: 2025-01-20
category: "personal"  # or "personal"
priority: 4
header_image: "/assets/images/tower.jpg"
description: "This website is an open-source way for students to share their projects. Learn how I made it!"
layout: "project"  # We'll create a project layout or use default
technologies:
  - HTML
  - CSS
  - Webdev
---

# Introduction

This page tests various Markdown (and inline HTML) formatting features to ensure your site's styling handles them well. Below are examples of **two columns**, **images** of different sizes and alignments, **code blocks**, **tables**, **text-wrapped images**, and an **embedded YouTube video**.

---

## Two Columns

Markdown doesn't have built-in column support, so you can use small HTML blocks:

<div class="two-col">
  <div>
    **Left Column**
    - Some bullet
    - Another bullet
  </div>
  <div>
    **Right Column**
    - Another list
    - More content
  </div>
</div>

---
## Examples of custom sized and justified images.
<img src="/assets/images/tower.jpg" alt="Avatar" class="float-left" style="width: 150px;" />
<img src="/assets/images/ranker_teaser.jpg" alt="Avatar" class="float-right" style="width: 150px;" />
<div style="clear: both;"></div>

## Another way of doing images
![Small Image](/assets/images/tower.jpg){: style="width:100px; text-align:right; margin-left:1rem;" }

<div style="text-align: right;">
    <img src="tower.jpg" alt="Example Image" />
</div>

## Code snippets

```python
def greet(name):
    print(f"Hello, {name}!")
    return f"Greeting for {name} created."
```



## embedding videos
remeber to add a clear style `<div>` or suffer the consequences.
<iframe width="480" height="240"
  src="https://www.youtube.com/embed/dQw4w9WgXcQ"
  title="YouTube video player"
  frameborder="0"
  style="text-align: center; margin: 10px;"
  allowfullscreen>
</iframe>
<div style="clear: both;"></div>

## Math
Inline math: \( a^2 + b^2 = c^2 \)
Different inline math: $x^2 +y^2 = z^2$

Display math:
$$
\frac{\partial}{\partial x} f(x,y) = 2x + y^2
$$
