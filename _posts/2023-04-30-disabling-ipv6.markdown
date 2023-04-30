---
layout: post
title:  "Disabling IPv6 on Linux using sysfs"
date:   2023-04-30
categories: linux
---

{% highlight shell %}
sudo -i
echo net.ipv6.conf.default.disable_ipv6=1 >> /etc/sysctl.conf
echo net.ipv6.conf.all.disable_ipv6=1 >> /etc/sysctl.conf
sysctl -p
{% endhighlight %}
