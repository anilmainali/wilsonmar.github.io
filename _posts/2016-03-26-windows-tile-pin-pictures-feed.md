---
layout: post
title: "Windows Tile pictures and feed"
excerpt: "So you can see your picture on Windows"
tags: [windows, mac, setup, testing]
image:
  feature: pic rainbow black apple logo 1900x500.jpg
  credit: Wallpaperscraft
  creditlink: https://wallpaperscraft.com/image/app_storm_apple_mac_rainbow_stripes_horizontal_8063_1920x1080.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

Windows 8 & 10 users can pin a website to their home screen.

Instructions here describe how to provide Windows with images for the different size tiles Windows uses.

0. See some examples of sites pinned on Windows 8 & 10 at
<a target="_blank" href="http://pinnedsitedemo.cloudapp.net/testdrive/index.aspx">http://pinnedsitedemo.cloudapp.net/testdrive/index.aspx</a>.

0. Go to <a target="_blank" href="http://www.buildmypinnedsite.com/en">http://www.buildmypinnedsite.com/en</a>

0. Specify a title for your site.

0. Specify a color.

0. Upload an image which the Microsoft site formats into different sizes within a zip file.

0. Crop the images online.

0. In "Add Notifications", specify the RSS feed URL. The RSS feed for this site is:

   <a target="_blank" href="http://wilsonmar.github.io/feed.xml">
   http://wilsonmar.github.io/feed.xml</a>

   (The XML is not that human-readable)

0. Download the zip file package

0. View each file to make sure they look OK.

0. PROTIP: Rename image file names with a "windows-" prefix so they appear together,
and enable you to remember what they're for.

0. Edit the downloaded <strong>browserconfig.xml</strong> file to rename its image file name references
before copying it to the root of your site.

0. Paste just one line in your site's landing page (index.md) &LT;head&GT; section.

   With a Jekyll site, edit the <strong>_head.html</strong> file within the _includes folder
   to add this among Webmaster Tools verification meta lines:

   {% highlight html %}
   <!-- For Microsoft Windows 8 & 10 pinned site with  browserconfig.xml and 4 windows-tile- png files -->
   <meta name="application-name" content="Wilson Mar"/>
   {% endhighlight %}

   Doing this would allow you to ignore what Microsoft's website also generates, such as:

   {% highlight html %}
<meta name="application-name" content="Wilson Mar"/>
<meta name="msapplication-TileColor" content="#000000"/>
<meta name="msapplication-square70x70logo" content="windows-tile-tiny.png"/>
<meta name="msapplication-square150x150logo" content="windows-tile-square.png"/>
<meta name="msapplication-wide310x150logo" content="windows-tile-wide.png"/>
<meta name="msapplication-square310x310logo" content="windows-tile-large.png"/>
<meta name="msapplication-notification" content="frequency=30;polling-uri=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=1;polling-uri2=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=2;polling-uri3=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=3;polling-uri4=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=4;polling-uri5=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=5; cycle=1"/>
   {% endhighlight %}


## Social media coloring

There's also: 

{% highlight html %}
<meta name="msapplication-TileColor" content="#000000"/>
{% endhighlight %}

   ## API

More about setup Live Tile Notifications:

https://msdn.microsoft.com/library/bg183312%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396
