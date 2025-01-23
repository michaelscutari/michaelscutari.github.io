---
title: "Website Demo"
date: 2025-01-20
category: "personal"  # or "personal"
priority: 6
header_image: "/assets/images/tower.jpg"
description: "This website is an open-source way for students to share their projects. Learn how I made it!"
layout: "project"  # We'll create a project layout or use default
status: "new"
technologies:
  - HTML
  - CSS
  - Webdev
---

# Introduction

I made this website to display a lot of the projects that I have worked on in more detail, but in many ways this site itself is a
project! My goal was to design something that other students and engineers could edit to be their own. The original repository
for this project can be found [here](https://github.com/michaelscutari/michaelscutari.github.io) and an example of someone else
using this repository already [here](https://isabeldudlyke.github.io)!

## Vision
Using GitHub Pages means that the site is completely free to host, and using Jekyll means that the site can be customized by
only editing Markdown documents. I currently still in the process of creating another repository with a tutorial that will
show people the basics of using Git and Markdown to create their own website.

## Creation
The whole website was created over the course of a long weekend. I am super happy with the result and would like to thank
[Shaan Yadav](https://shaan106.github.io) for the inspiration and motivation to get started with this project.

## Technical Specs
The website is built using Jekyll, a static site generator, with Liquid templating for dynamic content. It utilizes HTML5, CSS3, and JavaScript for structure, styling, and interactivity. The CSS incorporates responsive design principles, while JavaScript enables dynamic features like a hamburger menu and project filtering. Additional tools include MathJax for rendering LaTeX math and GitHub Pages for hosting. The layout is optimized with media queries and grid-based galleries.

## Content
This page tests various Markdown (and inline HTML) formatting features to ensure the site's styling handles them well and to
serve as a reference. Below are examples of **two columns**, **images** of different sizes and alignments, **code blocks**, **tables**, **text-wrapped images**, and an **embedded YouTube video**.

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
## Examples of custom sized and justified images
<img src="/assets/images/tower.jpg" alt="Avatar" class="float-left" style="width: 150px;" />
<img src="/assets/images/ranker_teaser.jpg" alt="Avatar" class="float-right" style="width: 150px;" />
<div style="clear: both;"></div>

## Another way of doing images
![Small Image](/assets/images/tower.jpg){: style="width:100px; text-align:right; margin-left:1rem;" }

<div style="text-align: right;">
    <img src="/assets/images/tower.jpg" alt="Example Image" />
</div>

<div style="display: flex; justify-content: center;">
    <img src="/assets/images/tower.jpg" alt="Example" />
</div>


<div style="display: flex; justify-content: right;">
    <img src="/assets/images/tower.jpg" alt="Example" />
</div>

## Code snippets

```python
def greet(name):
    print(f"Hello, {name}!")
    return f"Greeting for {name} created."
```

## Table

| Feature           | Description                              | Example                  |
|-------------------|------------------------------------------|--------------------------|
| **Responsive**    | Adjusts to screen sizes                 | Mobile-friendly layout  |
| **Customizable**  | Easily modify styles and content         | Edit Markdown and CSS   |
| **Open Source**   | Free to use and contribute               | GitHub Repository Link  |
| **Fast Loading**  | Optimized for performance               | Minimal external assets |

## Embedding videos
Remeber to add a clear style `<div>` or suffer the consequences.
<iframe width="480" height="240"
  src="https://www.youtube.com/embed/dQw4w9WgXcQ"
  title="YouTube video player"
  frameborder="0"
  style="text-align: center; margin: 10px;"
  allowfullscreen>
</iframe>
<div style="clear: both;"></div>

## Math
Inline math: $x^2 +y^2 = z^2$

Display math:
$$
\frac{\partial}{\partial x} f(x,y) = 2x + y^2
$$
