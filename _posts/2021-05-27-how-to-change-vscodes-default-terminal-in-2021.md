---
title:  "How to Change VSCode's Default Terminal in 2021"
excerpt: "#terminal.integrated.shell.windows# is now deprecated."
categories:
  - Study
tags:
  - IDE
---

# Motivation

Now that I've customized my Windows Terminal using the trendy [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh) and [powerlevel10k](https://github.com/romkatv/powerlevel10k), I also wanted to change the default terminal on VSCode.

![My Windows Terminal]({{ site.baseurl }}/assets/images/posts/2021-05-27-my-windows-terminal.png)

*Figure 1. My Windows Terminal*

Looks pretty, huh?

Then, I moved to settings on VSCode.

![VSCode setting]({{ site.baseurl }}/assets/images/posts/2021-05-27-vscode-settings.png)

*Figure 2. VSCode setting*

But <code>terminal.integrated.shell.windows</code> doesn't exist. I thought I probably could have done something wrong when installing VSCode. So I just tried typing  <code>terminal.integrated.shell.windows</code> into <code>settings.json</code>.

![Deprecated feature]({{ site.baseurl }}/assets/images/posts/2021-05-27-deprecated.png)

*Figure 3. Deprecated feature*

Then it showed me this message. I read it carefully but I was still confused. I somehow figured out how to change the default terminal in the new way!

# The new recommended way

![terminal.integrated.profiles.windows]({{ site.baseurl }}/assets/images/posts/2021-05-27-terminal.integrated.profiles.windows.png)

*Figure 4. terminal.integrated.profiles.windows*

Type <code>terminal.integrated.profiles.windows</code> and open it in <code>settings.json</code>.

![settings.json]({{ site.baseurl }}/assets/images/posts/2021-05-27-settings-json.png)

*Figure 5. settings.json*

Then, you see this screen (Figure 5).

Add a terminal profile of your choice to <code>terminal.integrated.profiles.windows</code> if it doesn't already exist:

```json
{
    "terminal.integrated.fontFamily": "MesloLGS NF",
    "terminal.integrated.profiles.windows": {
        "OhMyZsh": {
            "path": "C:\\Windows\\System32\\wsl.exe"
        },
        "PowerShell": {
            "source": "PowerShell",
            "icon": "terminal-powershell"
        },
        "Command Prompt": {
            "path": [
                "${env:windir}\\Sysnative\\cmd.exe",
                "${env:windir}\\System32\\cmd.exe"
            ],
            "args": [],
            "icon": "terminal-cmd"
        },
        "Git Bash": {
            "source": "Git Bash"
        }
    }
}
```

I added <code>"OhMyZsh"</code> at the top. The important thing here is that the name of the profile that'll be set to default shouldn't have spaces in it. For example, <code>"Oh My Zsh"</code> wouldn't work, but <code>OhMyZsh</code> would.

Then, go back to settings and type <code>terminal.integrated.defaultProfile.windows</code>, and open it in <code>settings.json</code>, which will lead you to this screen (the same screen but with another line at the end):

![defaultProfile]({{ site.baseurl }}/assets/images/posts/2021-05-27-defaultProfile.png)

*Figure 6. defaultProfile line has been added*

Then you type the new profile name between the quotation marks and **don't forget to save it**!

![The end]({{ site.baseurl }}/assets/images/posts/2021-05-27-the-end.png)

*Figure 7. The end*

Ta-da! Now I have a cool terminal on VSCode as well. If the new change doesn't appear, try restarting VSCode.

# Conclusion

This looks very simple but I needed to spend about an hour to figure it out. I hope this helps people who run into the same problem. Thanks for reading!