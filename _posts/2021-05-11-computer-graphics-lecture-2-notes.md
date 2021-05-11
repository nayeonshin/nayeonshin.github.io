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

![Vector]({{ site.baseurl }}/assets/images/posts/2021-05-11-vector.png)

*Figure 1. Vector image from the slides*

Usually written as $\vec{a}$ or in bold

Magnitude written as $\|\|\vec{a}\|\|$

- Length and direction. Absolute position not important (translated vectors are the same)
- Use to store offsets, displacements, locations
  - But strictly speaking, positions are not vectors and cannot be added: a location implicitly involves an origin, while an offset does not
  - Nevertheless, very convenient to also represent positions as vectors and to multiply them as matrices to do various transformations

### Vector operations

**1) Vector addition**

![Vector addition]({{ site.baseurl }}/assets/images/posts/2021-05-11-vector-addition.png)

*Figure 2. Vector addition image from the slides*

- Geometrically: Parallelogram rule
- In Cartesian coordinates (below), simply add coords
- Commutative: a + b is equal to b + a

**Cartesian coordinates**

![Cartesian coordinates]({{ site.baseurl }}/assets/images/posts/2021-05-11-cartesian-coords.png)

*Figure 3. Cartesian coordinates image from the slides*

The vector here can be moved to the origin of the Cartesian coordinate system.

- It has 4 units along the $X$ axis and 3 units along the $Y$ axis.

  → $A = 4X + 3Y$

  - $X$ and $Y$ here are coordinates of the axis
  - But in general, they can be any orthogonal unit vectors
    - Orthogonal: of or involving right angles; at right angles.

  $A = \left[x  y\right]$

  $A^T = \big(x  y\big)$

  $\|\|\vec{a}\|\| = sqrt(x^2 + y^2)$

**Vector multiplication**

- Dot product (or scalar product)

- Cross product

- Orthonormal bases and coordinate frames

- Note: we use right-handed (standard) coordinates

  ![Right hand rule]({{ site.baseurl }}/assets/images/posts/2021-05-11-right-hand-rule.png)

  *Figure 4. Right hand rule (Creator: corbac40 | Credit: Getty Images/iStockphoto)*

**Dot (scalar) product**

![Dot product]({{ site.baseurl }}/assets/images/posts/2021-05-11-dot-product.png)

*Figure 5. Dot product image from the slides*

$a \cdot b = b \cdot a$ (Commutative)

[To be continued]

### Matrices

