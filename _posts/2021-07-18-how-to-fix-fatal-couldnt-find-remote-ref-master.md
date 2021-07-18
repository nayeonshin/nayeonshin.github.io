---
title:  "How to Fix 'fatal: couldn't find remote ref master'"
excerpt: "GitHub updated the default branch's name."
categories:
  - Study
tags:
  - Git
---

## Background

I'm a Git noob but I use it extensively. The version control lets me keep track of my code changes and points to where I should fix. But when I tried to do `git pull origin master`, it always showed me this in the terminal:

![Git error]({{ site.baseurl }}/assets/images/posts/2021-07-18-git-error.png)

And every time I pushed to the `master` branch, it always made a new separate branch. And I didn't get it. Why the heck would it create another branch from the default branch?

## Solution

Then, I realized this:

![Main branch]({{ site.baseurl }}/assets/images/posts/2021-07-18-main-branch.png)

The default branch is named `main`, not `master`. This means, when you make a new repository and want to push to the central branch, you should **push to `main` branch**, unless you rename the default branch's name.

I think a lot of outdated articles still tell you to do something like `git pull origin master`. So, if you like to execute that command, you can rename your default branch:

![Branch menu]({{ site.baseurl }}/assets/images/posts/2021-07-18-branch-menu.png)

Click on the branch drop-down menu and go to `View all branches`.

![Branches page]({{ site.baseurl }}/assets/images/posts/2021-07-18-branches-page.png)

Then, you see the pencil icon. Click on it.

![Rename branch message]({{ site.baseurl }}/assets/images/posts/2021-07-18-rename-branch.png)

Type `master` and hit `Rename branch`. Then, you're all set! Now you can do `git pull origin master` to keep your local repository up-to-date, and you won't see `fatal: couldn't find remote ref master` in the terminal.

Thanks for reading, and I'll come back with another post!