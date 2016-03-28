---
layout: post
title: "Windows Tile Pin Picture to Website Feed"
excerpt: "So your picture can be on everyone's desktop all the time"
tags: [windows, mac, setup, testing]
image:
  feature: pic green grass windows 1900x475.png
  credit: Microsoft
  creditlink: http://dri1.img.digitalrivercontent.net/Storefront/Site/msusa/images/promo/Windows/en-US-Windows-Mod-A-Familiar-Better-desktop.jpg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

## Pin your website

Windows 8 & 10 users can pin a website URL to their home screen
such that when the tile is clicked, the site's XML feed is shown (formatted).

Instructions here describe how to provide Windows tiles with images for the different size tiles Windows uses.

0. See some examples of sites pinned on Windows 8 & 10 at
<a target="_blank" href="http://pinnedsitedemo.cloudapp.net/testdrive/index.aspx">http://pinnedsitedemo.cloudapp.net/testdrive/index.aspx</a>.

0. Go to <a target="_blank" href="http://www.buildmypinnedsite.com/en">http://www.buildmypinnedsite.com/en</a>

<img align="right" width="227" height="437" src="/images/scr windows tile pin 454x874.jpg">

0. Specify a title for your site.

0. Specify a color. The default is black (000000), but select white (FFFFFF) if your picture has a dark background.

0. Upload an image.

0. Crop the images online.

   | Crop size | Image size | Name   |
   | --------- | ---------- | ------ |
   | 128 x 128 | 128 x 128  | tiny   |
   | 270 x 270 | 198 x 198  | square |
   | 270 x 558 | 248 x 120  | wide   |
   | 558 x 558 | 248 x 248  | large  |

0. In "Add Notifications", specify the RSS feed URL. The RSS feed for this site is:

   <a target="_blank" href="http://wilsonmar.github.io/feed.xml">
   http://wilsonmar.github.io/feed.xml</a>

   (The XML is not that human-readable, but the lastest post is listed first.)

0. Download the zip file package which contains png files.

0. View each file to make sure they look OK.

0. PROTIP: Rename image file names with a "windows-" prefix so they appear together,
and enable you to remember what they're for.

0. Move the files in your <strong>/images</strong> folder.

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
<meta name="msapplication-square70x70logo" content="/images/windows-tile-tiny.png"/>
<meta name="msapplication-square150x150logo" content="/images/windows-tile-square.png"/>
<meta name="msapplication-wide310x150logo" content="/images/windows-tile-wide.png"/>
<meta name="msapplication-square310x310logo" content="/images/windows-tile-large.png"/>
<meta name="msapplication-notification" content="frequency=30;polling-uri=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=1;polling-uri2=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=2;polling-uri3=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=3;polling-uri4=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=4;polling-uri5=http://notifications.buildmypinnedsite.com/?feed=http://wilsonmar.github.io/feed.xml&amp;id=5; cycle=1"/>
   {% endhighlight %}

## Pin the site as Live Tile

0. In the Omni-search bar type in the URL. For this site: wilsonmar.github.io

   http:// is not needed.

0. Click the three dots at the upper-right corner to open the menu.

0. Select <strong>Pin to Start</strong>.

0. Click the Windows button for the Start screen.

0. Right-click on your website's picture to <strong>Resize</strong>.

0. Select Large (or another size).


## Social media coloring

There's also:

{% highlight html %}
<meta name="msapplication-TileColor" content="#000000"/>
{% endhighlight %}

   ## API

More about setup Live Tile Notifications:

https://msdn.microsoft.com/library/bg183312%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396

See the session <a target="_blank" href="https://channel9.msdn.com/Events/Build/2016/B803">
What’s New for Tiles and Toast Notifications</a>
at Build 2016 on April 1, 2016 by Lei Xu, who also did
spoke at Build 2015 session
<a target="_blank" href="https://channel9.msdn.com/Events/Build/2015/2-762">
Tiles, Notifications, and Action Center</a>.
