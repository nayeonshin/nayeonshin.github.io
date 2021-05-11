---
title:  "[UC San DiegoX CSE167x] Computer Graphics Lecture 2 Notes"
excerpt: "Brushing off basic Math for CG"
categories:
  - Study
tags:
  - Computer_Graphics
use_math: true
---

# UC San DiegoX CSE167x

[This](https://courses.edx.org/courses/course-v1:UCSDx+CSE167x+4T2015/information/) is a Computer Graphics course I found on edX. This post is the second post after [UC San DiegoX CSE167x] Computer Graphics Lecture 1 Notes.

# My notes

## Linear algebra

### Vectors

![image-20210511183133013]({{ site.baseurl }}/assets/images/posts/2021-05-11-vector.png)

*Figure 1. Vector image from the slides*

Usually written as $\vec{a}$ or in bold

Magnitude written as $\|\vec{a}\|$

- Length and direction. Absolute position not important (translated vectors are the same)
- Use to store offsets, displacements, locations
  - But strictly speaking, positions are not vectors and cannot be added: a location implicitly involves an origin, while an offset does not
  - Nevertheless, very convenient to also represent positions as vectors and to multiply them as matrices to do various transformations

### Matrices

