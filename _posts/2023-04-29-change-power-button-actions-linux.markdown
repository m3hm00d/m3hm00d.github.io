---
layout: post
title:  "Linux: Configure power button to lock the screen"
date:   2023-04-29
categories: linux
---

`/etc/systemd/logind.conf` listens for power press events, and then produces the configured messages on dbus. 

We would add `HandlePowerKey=lock` to this file. Rebooting the logind service kills the current login session too, so be careful.

Then install xss-lock. It is a utility that can hear for different power-related messages on dbus, and then do what we ask it to do when those messages are heard.

Add the following to `~/.config/i3/confg`:

{% highlight shell %}
exec --no-startup-id xss-lock --transfer-sleep-lock -- i3lock -f --color=181a1b --nofork
{% endhighlight %}
