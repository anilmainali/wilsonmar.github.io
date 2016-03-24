---
layout: post
title: "Clickable diagrams and maps in Jekyll posts"
excerpt: "Includes make me happy"
tags: [sample post, click maps, test]
comments: true
---
<i>{{ page.excerpt }}</i>

Clickable map:

<img src="https://cloud.githubusercontent.com/assets/300046/14015545/77b35900-f17f-11e5-83b7-f931da813eb2.gif" alt="Us states" usemap="#us-states" />
<map name="us-states">
{% for s in site.collections['us-states'] %}
<area shape="poly" coords="28,197,46,185,72,199,72,241,88,243,102,261,92,263,70,241,42,243,28,257,12,259,34,243,20,233,16,223,34,215,22,207,30,205,28,197"
    href="#AK" 
    alt="AK" title="State" >
{% endfor %}


<iframe src="https://www.makeaclickablemap.com/map.php?dd079c4716f558afc7fca114027f699f7c2c005f" frameborder="0" scrolling="no" height="720" width="960"></iframe>

TECHNNICAL NOTE: The above is within an iframe.

This is an upgrade of my terrible <a target="_blank" href="http://wilsonmar.com/1usa.htm">
Roadtrips to visit museums across the USA</a>

But I was not able to get them working by doing an include:


   &#123;% include us_states_museums.html %}


If you know me, I've got a bunch of complicated diagrams with lots of boxes and lines.

So I've been creating animations in PowerPoint, then recording explanations in videos 
that reveal each box and line.

That diagram on my website I would craft coordinates around each clickable area
(image maps in HTML and now in CSS).

Well, as of March 2016, GitHub hasn't gotten around to support click maps on graphics files.

## SVG if you have it

Scaled Vector Graphics stay sharp on all sizes.

   * http://freehtml5maps.com
   uses raphael javascript library to render the map in SVG or VML.

   * http://codecanyon.net/item/interactive-usa-map-html5/4527698
   asks $13 for its SVG scalable/responsive USA map.

{% highlight html %}
<svg version="1.1" id="Layer_1" xmlns="w3.org/2000/svg"; xmlns:xlink="w3.org/1999/xlink"; x="0px" y="0px" width="1343.791px" height="932.583px" viewBox="0 0 1343.791 932.583" enable-background="new 0 0 1343.791 932.583" xml:space="preserve"> <g id="Panama"> <path fill="#FDF9D1" stroke="#918E8F" d="..."/> </g> </svg> 
{% endhighlight %}

   * http://www.irunmywebsite.com/raphael/SVGTOHTML_LIVE.php

   * http://code.google.com/p/svg2imap/


## Making clickable maps
Several websites help in the tedious work of defining clickable areas:

   * https://makeaclickablemap.com

   * https://www.image-maps.com

Some examples make use of jQuery:

   * http://winstonwolf.pl
     is beautiful maps of European countries as well as the US.

   * http://www.outsharked.com/imagemapster/
     jQuery

Blogs about this topic:

   * http://www.cssplay.co.uk/articles/imagemap/

## Sites that have nice maps

http://www.samhsa.gov/medication-assisted-treatment/physician-program-data/treatment-physician-locator?field_bup_physician_us_state_value=OR

