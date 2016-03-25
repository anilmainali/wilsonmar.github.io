---
layout: post
title: "Appium mobile testing"
excerpt: "Functional test smart phones"
tags: [apple, mac, setup, testing]
image:
  feature: pic rainbow black apple logo 1900x500.jpg
  credit: Wallpaperscraft
  creditlink: https://wallpaperscraft.com/image/app_storm_apple_mac_rainbow_stripes_horizontal_8063_1920x1080.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


<a id="AppiumSetupz"></a>

## Appium Mobile Test Rig Setup


<p class="Action">
Install appium_console gem.
<pre>
gem uninstall -aIx appium_lib
gem uninstall -aIx appium_console
gem install --no-rdoc --no-ri appium_console
<pre>

<p class="Action">
Install flaky gem.
https://github.com/appium/flaky
(posix-spawn)
<pre>
gem uninstall -aIx flaky
gem install --no-rdoc --no-ri flaky
</pre>


