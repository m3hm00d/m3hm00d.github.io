---
layout: post
title:  "Installing Lineage OS on Mi device"
date:   2023-04-29
categories: android
---

Install adb and fastboot using `pacman -S android-tools`

Download Lineage image and TWRP recovery for your device.

After enabling debugger options, copy these files using:

{% highlight shell %}
adb push lineage.zip  'data/local'
adb push twrp  'data/local'
{% endhighlight %}

Put the device in fastboot mode using `adb reboot bootloader`. Then run `fasboot flash recovery twrp.img` to flash, and then `fastboot reboot` to reboot.

Boot to TWRP (how?). In the TWRP interface, browse to `lineage.zip` and hit `Install`.
