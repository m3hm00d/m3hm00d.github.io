---
layout: post
title:  "Auto-scale XFCE-based systems on libvirt"
date:   2023-11-04
categories: linux
---

Problem: Even after install `spice-vdagent`, XFCE-based VMs refuse to auto-scale when using libvirt. A possible solution is to add the following to either `~/.bashrc` or `~/.zshrc`:

{% highlight shell %}
xrandr --output Virtual-0 --auto
{% endhighlight %}

Now everytime you need to resize, just open a terminal. It's not perfect but gets the job done.


