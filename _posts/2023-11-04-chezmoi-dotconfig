---
layout: post
title:  "Managing dotfiles with chezmoi"
date:   2023-11-04
categories: linux
---

*Source:* https://www.chezmoi.io/quick-start/#using-chezmoi-across-multiple-machines

Install on Arch Linux using:

{% highlight shell %}
pacman -S chezmoi
{% endhighlight %}

Initialize `chezmoi` on your system using `chezmoi init`. This will create the required git repo at `$HOME/.local/share/chezmoi`.

Then add the dotfiles you want to track to `chezmoi` repo using `chezmoi add ~/.bashrc`, for example.

After adding all required dotfiles, you can do:

{% highlight shell %}
chezmoi cd # To cd to chezmoi config directory
git add . # To add all the added dotfiles to git repo
git commit -m "Initial commit"
{% endhighlight %}

To push the repo to github, first create the repo and then push the local repo:

{% highlight shell %}
git remote add origin https://github.com/m3hm00d/dotfiles.git
git branch -M pc
git push -u origin main
{% endhighlight %}

*Note:* You will need to setup SSH keys on the github repo settings before being allowed to push.

#### On the secondary machine

Instead of `init`ing an empty `chezmoi` repo, we can use `chezmoi init https://github.com/m3hm00d/dotfiles.git` to get the latest dotfiles.

You can use `chezmoi apply` to update the settings as defined in the `chezmoi` config files.

