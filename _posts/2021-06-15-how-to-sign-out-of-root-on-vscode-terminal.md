---
title:  "How to Sign Out of Root on VSCode Terminal"
excerpt: "It was disappointingly simple."
categories:
  - Study
tags:
  - IDE
toc: false
---

Okay lol this is going to be the shortest and most simple post ever.

When launching VSCode, I was signed in as the root user by default. (I'm using Window Subsystem for Linux, for your information.) I googled for an hour to figure out how to switch to a local user, but these were all not successful in the VSCode terminal:

<code>sudo su nayeonshin</code>

Control + D

<code>exit</code>

Ugh, I even tried re-installing VSCode but nothing worked. Then, I tried this in the Windows terminal:

<code>code .</code>

![VSCode local terminal]({{ site.baseurl }}/assets/images/posts/2021-06-15-vscode-terminal.png)

Ta-da. How easy was it? It was *disappointingly* easy.

Thanks for reading!
