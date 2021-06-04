---
title:  "Do Not Use IDs in CSS; Only Use Classes: BEM"
excerpt: "Stick to Block Element Modifier for semantic markup"
categories:
  - Study
tags:
  - Front-End
  - HTML/CSS
---

# Prerequisites

- Readers know the basics of HTML and CSS.

# Motivation

There are [methodologies for architecting CSS](https://valoremreply.com/post/5_css_methodologies/). You *can* use both IDs and classes to refer to HTML tags. But actually, it's not recommended to use IDs if you can avoid it. Let's find out why and what we can do instead.

# Sample code

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div id="container">
            <div id="container2">
                <span class="item"></span>
                <span class="item"></span>
                <span class="item"></span>
            </div>
            <div id="container3"></div>
        </div>
    </body>
</html>
```

```css
body {
    height: 100vh;
}

body, #container, #container2 {
    display: flex;
    justify-content: center;
    align-items: center;
}

#container {
    width: 300px;
    height: 300px;
    background-color: teal;
}

#container2, #container3 {
    margin: 10px;
    width: 100px;
    height: 100px;
    background-color: tomato;
}

.item {
    margin: 5px;
    width: 10px;
    height: 10px;
    background-color: yellow;
}

.item:nth-child(2) {
    width: 15px;
    height: 15px;
}

.item:last-child {
    width: 5px;
    height: 5px;
}
```

Let's say we have this code above that displays this on the screen:

![Sample shape]({{ site.baseurl }}/assets/images/posts/2021-05-27-sample-shape.png)

*Figure 1. Sample shape*

Look at CSS. We have IDs and a class, and it's hard to know what's inside what just by looking at the CSS code. And doesn't it look quite messy? We have to make sure we use <code>.</code> for classes and <code>#</code> IDs. This is quite troublesome.

# BEM (Block Element Modifier)

Therefore, BEM was introduced. BEM stands for Block Element Modifier. The idea is that we do not use IDs at all; we only use classes. And there are rules when naming a class.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div class="container">
            <div class="container__box">
                <div class="box__item"></div>
                <div class="box__item box__item--big"></div>
                <div class="box__item box__item--small"></div>
            </div>
            <div class="container__box"></div>
        </div>
    </body>
</html>
```

Here are the rules:

<code>block__element--modifier</code>

- Use {things are outside}<code>__</code>{things are inside}

  Examples from code above:

  - <code>container__box</code> is inside <code>container</code>

  - <code>box__item</code> is inside

    <code>container__box</code>

- Use <code>--</code> for modifiers

  Examples from code above:

  - <code>box__item--big</code>: the box item that we will set to be big
  - <code>box__item--small</code>: the box item that we will set to be small

And we look at the new CSS code:

```css
body {
    height: 100vh;
}

body, .container, .container > .container__box {
    display: flex;
    justify-content: center;
    align-items: center;
}

.container {
    width: 300px;
    height: 300px;
    background-color: teal;
}

.container__box {
    margin: 10px;
    width: 100px;
    height: 100px;
    background-color: tomato;
}

.box__item {
    margin: 5px;
    width: 10px;
    height: 10px;
    background-color: yellow;
}

.box__item--big {
    width: 15px;
    height: 15px;
}

.box__item--small {
    width: 5px;
    height: 5px;
}
```

![Sample image created with new CSS]({{ site.baseurl }}/assets/images/posts/2021-05-27-sample-shape-with-new-css.png)

*Figure 2. Sample shape created with new CSS*

This looks a lot more semantic than the original CSS code. We can tell things like <code>box__item</code> is inside something that has <code>box</code> in its name,

which is <code>container__box</code> without having to look at HTML code.

<code>.box__item--big</code> has larger width and height, and using the class name that has <code>--small</code> in it we can set the particular item smaller.

If you want to read more about BEM, [read this](http://getbem.com/naming/).

# Conclusion

We use BEM (Block Element Modifier) to write semantic markup code, which is our main task as programmers.

If you have questions or feedback, please feel free to leave a comment. Thanks for reading!