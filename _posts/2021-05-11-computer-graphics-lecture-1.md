---
title:  "[UC San DiegoX CSE167x] Computer Graphics Lecture 1 Notes"
excerpt: "My first CG course"
categories:
  - Study
tags:
  - Computer_Graphics
---

# UC San DiegoX CSE167x

[This](https://courses.edx.org/courses/course-v1:UCSDx+CSE167x+4T2015/information/) is a Computer Graphics course I found on edX. I was looking at multiple free online lectures about Computer Graphics, but I wasn't able to find a good one. This course seems to be fairly good to start with.

# My notes

- Rendering: the process of creating realistic images

- Two main goals of the course

  1. Systems: write complex 3D graphics programs (real-time scene viewer in OpenGL, offline raytracer)
     - OpenGL: Graphics API
     - Offline ray tracing: enables you to create realistic images of 3D scenes by tracing rays that arise from the camera and go through each pixel in the image
  2. Theory: mathematical aspects and algorithms underlying modern 3D graphics systems

  - This course is not about the specifics of 3D graphics programs like Maya, Alias, DirectX but about the concepts underlying them. You will write programs in OpenGL/GLSL

- Why study 3D Computer Graphics?

  - Applications
    - Movies
      - Toy Story (1995) by Pixar: the first completely Computer Graphics movie
    - Games
    - Computer Aided Design (CAD)
    - Lighting Simulation (Interiors, Automobiles, ...)
    - Visualization (Scientific, Medical)
    - Virtual Reality
  - Fundamental intellectual challenges
    - Create and interact with realistic virtual world
    - Requires understanding of all aspects of physical world
    - New computing methods, displays, technologies
  - Technical challenges
    - Math of (perspective) projections, curves, surfaces
    - Physics of lighting and shading
    - 3D graphics software programming, hardware

- Digital Visual Media

  - From text to images to video (to 3D?)
  - Image and video processing and photography
  - Flickr, YouTube, WebGL
  - Real, Virtual Worlds (Google Earch, Second Life)
  - Electronic publishing
  - Online gaming
  - 3D printers and fabrication

---

- 3D Graphics Pipeline
  - Modeling: process of creating geometric models of objects we're interested in
  - Animation
  - Rendering
    - Simulate the way the light propagates in the scene to create effects like realistic and intricate shadow details
- Rasterization & raytracing: two different ways in which you can create images
  - Rasterization: goes through all the geometric primitives and determines where in the screen they should go
  - Raytracing: the opposite thing which goes to each point or pixel in the screen and determines which geometric primitive that corresponds to
    - Can produce higher quality images but has historically been slower
- GPU (Graphics Programming Unit)

---

- Computer Graphics: term coined by William Fetter of Boeing in in 1960
  - The first graphics systems were developed in the mid-1950s, the US Air Force SAGE radar systems

1. Text: major development in CG

2. From text to GUIs (Graphical User Interface)

3. Paint systems

4. Image processing

5. Modeling

   - Geometric modeling: process of creating 3D geometry, which can then be used in a CG system
     - One of major developments: creation of spline curves and surfaces

6. Rendering: 1960s (Visibility)

   - Fundamental challenge of visibility: which object is before which object

7. Rendering: 1970s (Lighting)

   - Gouraud shading

8. Rendering (1980s, 90s: Global illumination)

   