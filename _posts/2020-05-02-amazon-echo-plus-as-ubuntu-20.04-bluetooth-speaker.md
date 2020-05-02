---
layout: post
title:  "Amazon Echo Plus as bluetooth speaker on Ubuntu 20.04"
date:   2020-05-02 14:14:12 +0100
categories: guides
comments: true
---
Yesterday, I tried to use my Amazon Echo Plus as bluetooth speaker on my media center Running Ubuntu 20.04.

I paired the Echo Plus using Alexa app on my phone following these steps:

1. Open Alexa app on your phone and go to `devices` tab, then `Echo & Alexa`.
2. Choose your Echo Plus from list and then the gear icon on top left.
3. Under `Wireless` tab, choose `Bluetooth Devices` and then `Pair new device`. Now the Echo Plus is in Pairing Mode.
4. On Ubuntu, discover devices with Bluetooth and then pair `Echo-s5u`

Following these steps, paired was successful but _I couldn't send any audio to Echo Plus_.

Why? Because the Echo was recognized as microphone instead of a speaker.

The only workaround I found at the moment to avoid this, is to **pair the Echo Plus while you're playing some audio on your Ubuntu machine**.

I just unpaired the devices, then started a YouTube video on my Ubuntu machine and then repeated the steps above.
A that poin I've been able to send audio to my Echo Plus.
