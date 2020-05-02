---
layout: post
title:  "Fixing bluetooth headphones (HFP/HSP) on Ubuntu 18.04"
date:   2020-01-14 17:31:18 +0100
categories: guides
comments: true
---
For years I have had a problem with my Bluetooth headphones.
Although everything works correctly if headphones are connected in A2DP mode, problems start to arise when I try to use them in HSP/HFP mode.
As soon as this mode is activated, I begin hearing an audio loopback (coming from the microphone) and nothing else.
Naturally, the microphone itself also doesn't work.

After discovering the chip:
{% highlight bash %}
$ lsusb | grep Bluetooth
# Bus 003 Device 002: ID 0b05:17cb ASUSTek Computer, Inc. Broadcom BCM20702A0 Bluetooth
{% endhighlight %}

I have searched for messages related to Bluetooth firmware.
{% highlight bash %}
dmesg | grep -i bluetooth | grep -i firmware -A2
# Bluetooth: hci1: Direct firmware load for brcm/BCM20702A1-0b05-17cb.hcd failed with error -2
# Bluetooth: hci1: BCM: Patch brcm/BCM20702A1-0b05-17cb.hcd not found
{% endhighlight %}

At this point the error is clear enough.
After a brief search I found the necessary driver [here][bt-firmware], and I copied it to the `/lib/firmware/brcm` folder.
After a reboot, for the first time in a year now, I managed to use the headphones in HSP/HFP mode.

[bt-firmware]: https://github.com/winterheart/broadcom-bt-firmware
