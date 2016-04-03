---
layout: post
title: "Jekyll site development"
excerpt: "The most popular"
tags: [website, builder, simplicity, jekyll]
image:
  feature: scr white jekyll static tools 1900x500.jpg
  credit:
  creditlink:
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

Jekyll is currently the
[most popular among static site builder options](/static-websites).


## Jekyll Themes

One of the nice things about WordPress and other CMS is one doesn't need to start from scratch.

Same with Jekyll.

The structure of posts makes it easy to move it to any number of other Jekyll themes with only a few edits.

### Jekyll Theme shops
To see responsive websites, get to it quicker on your mobile smartphone QR code is provided for you.

* <a target="_blank" href="http://jekyll.tips/templates/">jekyll.tips/templates</a>

Within the Jekyll repository on GitHub:

   * <a target="_blank" href="https://github.com/jekyll/jekyll/wiki/Themes">
    github.com/jekyll/jekyll/wiki/Themes</a>

   Premium (paid) themes so you get updates and support, for less than $30.

   * <a target="_blank" href="http://jekyllthemes.io">jekyllthemes.io</a>

     This is an affiliate for other sites offering the same themes for less.

   * <a target="_blank" href="http://jekyllthemes.org">jekyllthemes.org</a>

### Themes from Michael Rose

Content on this website was created by editing markdown text (index.md files)
stored on GitHub.com.
The HTML sent to your browser for display is generated from markdown using
Ruby running [Jekyll](http://jekyllrb.com/) 3.0 rendering modifications of the
<a target="_blank" href="https://github.com/mmistakes/minimal-mistakes/">
minimal-mistakes theme from GitHub</a> by Michael Rose.

Michael also created the
<a target="_blank" href="https://github.com/mmistakes/skinny-bones-jekyll">
skinny-bones-jekyll theme demo</a> forkable
<a target="_blank" href="https://mmistakes.github.io/skinny-bones-jekyll/">
from GitHub</a>.
It features more use of graphics, and allows for localization.

The comparison:

| Feature          | HPSTR   | Minimal | Skinny | Simple |
|:-----------------|:-------:|--------:|-------:|-------:|
| External links   | YES     | -       | -      | -      |
| Floating menu    | YES     | -       | -      | -      |
| Gallery layout   | -       | -       | YES    | -      |
| Localization     | -       | -       | YES    | -      |
| Multiple authors | -       | YES     | -      | -      |
| Page TOC         | -       | YES     | -      | -      |
| Pages/Articles   | -       | *       | YES    | YES    |
| Posts            | YES     | YES     | YES    | YES    |
| Pagination       | YES     | -       | -      | -      |
| Rakefile.rb      | YES     | -       | -      | -      |
| Reading time     | YES     | -       | -      | -      |
| Tags list        | YES     | -       | -      | -      |
| Site search      | -       | -       | -      | YES    |
| Social icons only| -       | -       | -      | YES    |
| Social names     | YES     | -       | -      | -      |
| Timezones        | YES     | -       | -      | -      |

All the themes feature:

   * YAML front matter in index.md files processed by Jekyll
   * 404.md
   * feed.xml generation
   * Disqus support
   * Use of SASS
   * Theme setup page from the main menu / tab
   * Links to major social sites

Micheal blogs about his themes at
https://mademistakes.com/articles/using-jekyll-2016/


## Installation and Generation
Michael Rose presents a concise description of
<a target="_blank" href="https://mmistakes.github.io/minimal-mistakes/theme-setup/">
how to install the minimal-mistakes theme</a>.
This post augments and clarifies it.

Begin by making a folder and populating it on my local machine.

There is both a Master branch and a Develop branch.

I don't care about all the change history, so I click "Download ZIP"
and unzip it into that folder rather than:

    git clone https://github.com/mmistakes/minimal-mistakes.git

### Grunt tasks
After downloading, have Maven pull in dependencies based on the Gemfile:

   bundle install

Behind the scenes is a running of the **Gruntfie.js** that comes with the theme.
It defines the parameters of various tasks that are downloaded:

* <a target="_blank" href="https://github.com/gruntjs/grunt-contrib-clean">clean</a>
clears files and folders.
* <a target="_blank" href="https://github.com/gruntjs/grunt-contrib-jshint">jshint</a>
validates files with JSHint, based on the **.jshintrc** configuration file at the root folder.
* <a target="_blank" href="https://github.com/gruntjs/grunt-contrib-uglify">uglify</a>
minfies files with UglifyJS.
* <a target="_blank" href="https://github.com/gruntjs/grunt-contrib-watch">watch</a>
runs tasks whenever watched files change.
* <a target="_blank" href="https://github.com/gruntjs/grunt-contrib-imagemin">imagemin</a>
minifies PNG graphics files.
* <a target="_blank" href="https://github.com/sindresorhus/grunt-svgmin">grunt-svgmin</a>
minifies SVG graphics files.

NOTE: File names beginning with a dot are hidden.


## Serve Jekyll landing page

Theme programming goes to work generating HTML files in folder **_site**
when this command is issued when the present working directory is the
site's folder:

<a name="invoke-server"></a>

    bundle exec jekyll serve

To see the site the way GitHub would generate it
(without additional plug-ins some templates provide):

    bundle exec jekyll serve --safe

   The precise version of plug-ins used by GitHub on-line is listed
   <a target="_blank" href="https://pages.github.com/versions/">here</a>.

PROTIP: Leave this terminal instance running and open another Terminal
instance to work on the content of the site.

The generated HTML files can then be accessed from an internet browser
at this URL:

* <a target="_blank" href="http://localhost:4000">http://localhost:4000</a>

The landing page of the site is defined in the **index.md** file at the root folder.

{% highlight text %}
---
layout: home
excerpt: "By Wilson Mar"
tags: [Jekyll, theme, responsive, blog, template]
image:
feature: sunrise-1900x500.png
   credit:
   creditlink:
---
{% endhighlight %}

This "front matter" is standard for Jekyll sites.
Jekyll converts index.md files to index.html files.

The theme's programming put the value from tags: key in the HTML presented to users:

{% highlight html %}
<meta name="keywords" content="Jekyll, theme, responsive, blog, template">
{% endhighlight %}

TODO: Substitute the image file name in the **feature:** variable
with an alternative file you placed in the **images** folder.


Return to this page from any other by clicking on the site's title this theme
presents at the upper left corner.


## Change README.md content
The text in the README.md file at the root is not shown on the website.

It was written for those who work with the site's code, not readers of the resulting website.

So the content of this page should be changed from being about the theme
to about the website derived from the theme template, such as:

    "I hope you'll file an issue or send a Pull Request. I need the help."

File mm-theme-post-600.jpg within the images folder can be deleted.


## Tabs, folders, and index.md files (for SEO)

"About" and other **tabs** displayed constantly at the top of the page
are clickable. The pages they link to are specified in
the **navigation.yml** file within the **_data** folder:

{% highlight text %}
- title: About
url: /about/

- title: Sample Posts
url: /posts/
{% endhighlight %}

The **title:** key specifies the text of each tab, such as "About".
NOTE: CSS in the theme automatically turns all letters into capital.


github:
repo:  https://github.com/user/Proj # "GitHub project" link on sidebar


Next let's use a text editor to look into that **about** folder specified in the .yml file.


### index.md under folders

Jekyll converts the contents of each **index.md** file (containing markdown text)
into **index.html** files containing HTML.

Open the **index.md** file in the about folder.

HOORAY: The use of folders above an index.html file enables
calls using SEO-friendly links. For example, to reference the
about link:

   http://localhost:4000/about

HOORAY: This technique does not require use of mechanisms in the underlying web server container
(such as IIS).

The text is added to page titles that appear in browser tabs through this HTML:

{% highlight text %}
<title>All Posts &#8211; WilsonMar.GitHub.io</title>
{% endhighlight %}


### Parsing of post file names

The **posts** tab link to files within the **_posts** folder.
In the case of the sample file named "2011-03-10-sample-post.md",
Jekyll programming parses the "sample-post" out of the file name and uses that
as if it's named "sample-post.html".


### Metadata within .md files

At the top of each markdown file, between a set of 3 dashes,
are key-value pairs providing metadata about the page, such as this example
from the **index.md** file within folder **about**:

{% highlight text %}
---
layout: page
title: About
tags: [about, Jekyll, theme, responsive]
modified: 2014-08-08T20:53:07.573882-04:00
comments: true
image:
   feature: pic pic blue black stars spin 1900x500.jpg
   credit: Jeremy Thomas
   creditlink: https://www.flickr.com/photos/132218932@N03/page2
---
{% endhighlight %}

EXTRA: Detailed YAML specifications are at:
http://www.yaml.org/spec/1.2/spec.html


HOORAY: Such metadata takes the place of a database referenced to dynamically generate pages (as WordPress does).
Jekyll's lack of a database vastly simplies matters and speeds up processing.
This enables static page HTML to be distributed
in CDNs (Content Distribution Networks) around the world.
That maximizes download speed for visitors.

### Layout types

The various layout types are defined in files (with no extension) within the **_templates** folder:

* archive
* page
* post

HOORAY: This approach enables additional types to be defined.

{% highlight text %}
---
layout: {{ layout }}
title: {{ title }}
modified:
categories: {{ dir }}
excerpt:
tags: []
image:
feature:
---
{% endhighlight %}

Text within square braces define an array of several values.

### Liquid engine

Tags within &#123; curly braces &#125; are processed by the **Liquid** templating engine.

Liquid can perform if/then/else decisions and loops.

EXTRA: More detail about Liquid is at:
https://docs.shopify.com/themes/liquid/basics#If_.2F_Else_.2F_Unless


### Link icon YAML

In the list of posts, post titles with a link icon get that way because in its YAML is a line
link post line such as this:

{% highlight text %}
link: http://www.wilsonmar.com
---
{% endhighlight %}


### .yml metada

Default values are specified in a **_config.yml** file at the root of the site folder.

EXTRA: All keys are detailed at http://jekyllrb.com/docs/configuration/

Here are the first few lines of a sample file:

{% highlight text %}
# Site wide configuration

title:            WilsonMar.GitHub.io
locale:           en_US
url:

# Jekyll configuration

permalink:   /:categories/:title/
markdown:    kramdown
highlighter: rouge
sass:
sass_dir: _sass
style: compressed
gems:
- jekyll-sitemap
- jekyll-gist
{% endhighlight %}


PROTIP: Changes in the _config.yml file are applied only when the Jekyll service is recycled.
At the command terminal window where Jekyll was launched,
press control+C, then invoke the
<a href="#invoke-server">command to start the server again</a>.

Another theme (Poole Hyde) adds:

{% highlight text %}
---
github:
repo:  https://github.com/user/Proj # "GitHub project" link on sidebar
---
{% endhighlight %}


### sitemap.xml in _site

Theme programming also generates the **_site** folder and in it
generates **feed.xml** and **sitemap.xml** files for web crawlers to read.

### Bing it on
TODO: Get a value for the **bing-verify:** variable in your **_config.yml**.

0. Open a Webmaster Tools account at
<a target="_blank" href="http://www.bing.com/toolbox/webmaster/">bing.com/toolbox/webmaster/</a>

0. Sign In with a Windows Live ID. If you don't have a Microsoft account already, get one.

0. Type in your Site Name (mine's wilsonmar.github.io) and click Add a site.

0. Type in the URL to your Site Map. (mine's http://wilsonmar.github.io/sitemap.xml).

   The sitemap.xml file is generated in the **_site** folder,
   but will be the root folder when deployed on a web server.

0. Fill out the other fields (contact info and preferences), then click Save.

0. In the Verify ownership page, copy the string from:
   {% highlight text %}
   <meta name="msvalidate.01" content="73A60A207FC7D42B6F428E462079B001" />
   {% endhighlight %}

0. Paste that string to the right of the **bing-verify:** variable.

0. Click the **BingSiteAuth.xml** link to save the file.
0. Move the file into the root folder where the _config.yml file is
   (NOT in the _site folder, which gets deleted and repopulated automatically).

0. Recycle the Jekyll server to see the **BingSiteAuth.xml** in the _site folder.


### Google Ownership

This is explained in https://support.google.com/webmasters/answer/35179?hl=en

0. Access <a target="_blank" href="https://www.google.com/webmasters/tools/home?pli=1">
Webmasters Tools</a> using your Google account.

0. Add a Property (such as http://wilsonmar.github.io).

0. Download the html file (such as google923b0745fb3293c1.html) to the Downloads folder.

0. Move the file into the root folder where the _config.yml file is
(NOT in the _site folder, which gets deleted and repopulated automatically).

0. Download the file.


### Disqus comments

0. Use an internet browser to get to:
<a target="_blank" href="https://disqus.com/">
Disqus.com</a>.

This is about creating a publisher account such as "wilsonmarcom".

0. PROTIP: Create a separate personal commenter account (such as "wilsonmar")
   to track your responses on other websites.

0. Click the cog next to your picture to select **Add Disqus To Site**, or
https://publishers.disqus.com/engage?utm_source=Home-Nav

0. Click **Install on your site**.

0. Specify a site name such as "wilsonmar-github-io".

0. Click Next and answer the demographic questions (how many visits, etc.).

0. You don't need to
   select installation for Universal code and copy
   paste JavaScript because the theme has already done that in
   file **_disqus_comments.html** within folder **_includes**.

0. Copy the **site.owner.disqus-shortname**, such as "wilsonmargithubio" from:

{% highlight html %}
<script id="dsq-count-scr" src="//wilsonmargithubio.disqus.com/count.js" async></script>
{% endhighlight %}

0. Open for edit file **_config.yml** in the root folder.

0. Paste the Disqus short name as the value to key **disqus-shortname:**.

0. Read more about configuration of Disqus at:
   https://help.disqus.com/customer/en/portal/articles/2158629

<a target="_blank" href="https://disqus.com/admin/create/">
Disqus Setup Disqus on a New Site</a>.



<hr />

### Multiple authors

Lower in the file is information about the default author displayed on all pages.
This can be overridden in a particular index.md or post file by a line such as:

{% highlight text %}
author: billy_rick
{% endhighlight %}

"billy_rick" is a key to more information in the **authors.yml** file within the **_data** folder:

{% highlight text %}
billy_rick:
  twitter: @billyrick
{% endhighlight %}

HOORAY: This mechanism presents the photo and links to multiple alternative authors to appear on the website.


### Social links +

If you'd like more links, add them in folder **_includes** file **_author-bio.html**:

{% highlight html %}
{% if author.soundcloud %}<a href="http://soundcloud.com/{{ author.soundcloud }}" class="author-social" target="_blank"><i class="fa fa-fw fa-soundcloud"></i> Soundcloud</a>{% endif %}
{% endhighlight %}


### Social sharing

On the bottom of every page of the minimal-mistakes theme are large buttons for sharing
tweets, Facebook, and Google.


Unlike links on the left pane of every page,
clicking on these links pops up a new browser window.

You can change that pre-populated text (the URL) by changing the
**_social-share.html** file withing folder **_includes**.
The default pulls in the value of variables:

{% highlight text %}
{{ site.url }} and {{ page.url }}
{% endhighlight %}

The pop-up relies on cookies previously created when the visitor signed into Twitter, Facebook, and Google
on the same browser used to access this site.

<hr />

## Images
Images can be defined in GFM or standard HTML.

### In-line GFM images
Positioning of GFM-specified images can be specified using a special tag.

{% highlight html %}
![Smithsonian Image]({{ site.url }}/images/3953273590_704e3899d5_m.jpg)
{: .image-pull-right}
{% endhighlight %}

renders as:

![Smithsonian Image]({{ site.url }}/images/pic flood of daya 877x524.jpeg)
{: .image-pull-right}

NOTE: Most images are stored in the site's **images** folder.


### Clickable images
GFM is not yet able to handle code to specific clickable images,
either as HTML image maps nor as CSS.


#### One Up

{% highlight html %}
<figure>
<a href="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_b.jpg"><img src="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg"></a>
<figcaption><a href="http://www.flickr.com/photos/80901381@N04/7758832526/" title="Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr">Figure: Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr</a>.</figcaption>
</figure>
{% endhighlight %}

renders to:

<figure>
<a href="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_b.jpg"><img src="http://farm9.staticflickr.com/8426/7758832526_cc8f681e48_c.jpg"></a>
<figcaption><a href="http://www.flickr.com/photos/80901381@N04/7758832526/" title="Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr">Figure: Morning Fog Emerging From Trees by A Guy Taking Pictures, on Flickr</a>.</figcaption>
</figure>


#### Half/Three Up
The theme has a `half` class to split the available horizonatl space in half
to display two images side by side (and share the same caption).

{% highlight html %}
<figure class="half">
<a href="/images/image-filename-1-large.jpg"><img src="/images/image-filename-1.jpg"></a>
<a href="/images/image-filename-2-large.jpg"><img src="/images/image-filename-2.jpg"></a>
<figcaption>Figure: Two images.</figcaption>
</figure>
{% endhighlight %}

renders to:

<figure class="half">
<a href="http://placehold.it/1200x600.JPG"><img src="http://placehold.it/600x300.jpg"></a>
<a href="http://placehold.it/1200x600.jpeg"><img src="http://placehold.it/600x300.jpg"></a>
<figcaption>Figure: Two images.</figcaption>
</figure>

#### Three Up

The theme has a `third` class to split the available horizontal space in thirds
to display three images side by side (and share the same caption):

{% highlight html %}
<figure class="third">
<img src="/images/image-filename-1.jpg">
<img src="/images/image-filename-2.jpg">
<img src="/images/image-filename-3.jpg">
<figcaption>Figure: Three images.</figcaption>
</figure>
{% endhighlight %}

is rendered as:

<figure class="third">
<img src="http://placehold.it/600x300.jpg">
<img src="http://placehold.it/600x300.jpg">
<img src="http://placehold.it/600x300.jpg">
<figcaption>Figure: Three images.</figcaption>
</figure>


### Layout responsive to screen size
The MadeMistakes themes make use of the
<a target="_blank" href="http://semantic.gs/">Semantic Grid System</a>
to define fluid grids for each major page layouts with a few lines of CSS code referencing
@media queries.
This makes the theme responsive -- adapting to various size screens:

* Desktop default (up to the largest HD & 4XHD screen)

   Min-width: 780px

* Tablet Portrait (to landscape and desktop)

    Min-width: 768px / Max-width: 979px

* Smartphone (and all smaller screens)

    Max-width: 480px


### Image sized to screen?

The size of screens.

The image for **Twitter Cards** is a square image around 120 x 120 pixels.



<hr />

## Markdown coding
The next few sections are based on

https://mmistakes.github.io/minimal-mistakes/sample-post/

### Notice boxes
To put text in a box, add `{: .notice}` under the text to be boxed:

{% highlight text %}
**CAUTION:** Invalid markup can crash the server.
{: .notice}
{% endhighlight %}

renders to:

**CAUTION:** Invalid markup can crash the server.
{: .notice}

PROTIP: Make a small change (one phrase) then verify rendering.
Commit to git at every verified set.

### Blockquotes

A leading *>* marks a line as a blockquote:

{% highlight html %}
> Lorem ipsum
{% endhighlight %}

renders as:

> Lorem ipsum

### Footnotes
A paragraph ending with the &Vcirc; "circumflex" character (upper case of the number 6 key)
between square brackets defines the footnote number:

Footnotes are Syntax Highighting[^1].

A repeat of the sequence at the **beginning** of a paragraph defines the definition:

{% highlight yaml %}
[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>
{% endhighlight %}
[^1]: <http://en.wikipedia.org/wiki/Syntax_highlighting>



### Button colors in HTML
Use pre-defined classes:

{% highlight html %}
<div markdown="0"><a href="#" class="btn">Primary Button</a></div>
<div markdown="0"><a href="#" class="btn btn-success">Success Button</a></div>
<div markdown="0"><a href="#" class="btn btn-warning">Warning Button</a></div>
<div markdown="0"><a href="#" class="btn btn-danger">Danger Button</a></div>
<div markdown="0"><a href="#" class="btn btn-info">Info Button</a></div>
{% endhighlight %}

renders to:

<div markdown="0"><a href="#" class="btn">Primary Button</a></div>
<div markdown="0"><a href="#" class="btn btn-success">Success Button</a></div>
<div markdown="0"><a href="#" class="btn btn-warning">Warning Button</a></div>
<div markdown="0"><a href="#" class="btn btn-danger">Danger Button</a></div>
<div markdown="0"><a href="#" class="btn btn-info">Info Button</a></div>

If you are viewing this on a desktop, mouse-over each button to see the color change.

To change the colors, edit in folder **_sass** file **variables.scss**.

### Paragraph Indents
By default, the theme assumes formatting is for books by removing extra lines and adds indents to
second and subsequent paragraphs. Well, we're in the internet age where long paragraphs are the exception.

To disable the indents and add spacing between paragraphs,
edit in folder **_sass** file **variables.scss** to change:

    $paragraph-indent: true !default;

To:

    $paragraph-indent: false;

PROTIP: This change in the theme enables use of indented items using GFM.


### Numbered lists
As with GFM, numbers in front of ordered list items can be preceded by zeros since they are automatically numbered:

{% highlight text %}
0. Item one
0. sub item one
0. sub item two
0. Item two

some text after 3 spaces.

0. Item three
{% endhighlight %}

renders to:

0. Item one
0. sub item one
0. sub item two
0. Item two

some text after 3 spaces.

0. Item three



### Code Snippets
Instead of a set of three back quotes, blocks of programming code are enclosed with special tags like this:

<pre><code>
&#123;% highlight css %}
#container {
float: left;
margin: 0 -240px 0 0;
width: 100%;
}
&#123;% endhighlight %}
</code></pre>

renders as:

{% highlight css %}
#container {
float: left;
margin: 0 -240px 0 0;
width: 100%;
}
{% endhighlight %}


### Gists
Snippets of code on Gist.com can be displayed on the web page with a simple line
containing the gist.com userid and snippet number:

<pre><code>
&#123;% gist userid/6589546 %}
</code></pre>

renders to:

{% gist mmistakes/6589546 %}


### Standard GFM mark-up
Several coding techniques ar the same as in GitHub Flavored Markdown.

* Asterisks precede text in unordered lists preceded with bullets.
* The number of # characters preceding heading text specifies the level.
* One asterisk enclosing text makes it *italics*.
* Two asterisk enclosing text makes it **bold**.

Just as with GFM, regular HTML is recognized and processed as such.

{% highlight html %}
<strong>bolded text</strong>
{% endhighlight %}


### Custom Includes
Jekyll can process several special tags beyond what GFM can do.
An entire HTML file can be inserted:

<pre><code>
&#123;% include _toc.html %}
</code></pre>

The tag is processed by <a target="_blank" href="http://kramdown.gettalong.org/converter/html.html#toc">
Kramdown</a> which generates the Table of Contents displayed on the right side of the screen.

A custom include can be coded within markdown like this:

<pre><code>
&#123;% include evangelist_links.html %}
</code></pre>

Doing this takes some mental contortion because of the automatic processing.

The **evangelist_links.html** file referenced needs to be in the _includes folder.

     During processing, the folder "_includes" is automatically added to the link.
     Therefore you can't put the include file anywhere else, or you'll get a message such as:

     Error: Included file '_includes/includes/1loadrun_map.html' not found

However, there can be markdown in the **evangelist_links.html** file, such as:

{% highlight html %}
In this series:

* [Budget](Budget)

<!--
* [Future1](Future1)
-->
{% endhighlight %}

NOTE: HTML code above to ignore can be included in the file.


### Tables
A rule can be specified for formatting tables coded in GFM:

{% highlight text %}
| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}
{% endhighlight %}

renders to:

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}




<hr />

## Affiliate Ads

### Amazon Affiliate Ads

0. https://affiliate-program.amazon.com/gp/associates/network/main.html

0. Search for a product to get its URL, such as:
   http://www.amazon.com/gp/product/B00IR2VEUS/
   So Amazon's product code is  "B00IR2VEUS".

0. Specify the product code to get the HTML containing your affiliate tracking code, such as:

{% highlight html %}
<a target="_blank" href="http://www.amazon.com/gp/product/B00IR2VEUS/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B00IR2VEUS&linkCode=as2&tag=wilsonslifenotes&linkId=LGM2HVV7JYHE5QRS">Cabin Max Metz Backpack Flight Approved Carry on Bag 44 Litre Travel Hand Luggage - 55x40x20 (Black)</a><img src="http://ir-na.amazon-adsystem.com/e/ir?t=wilsonslifenotes&l=as2&o=1&a=B00IR2VEUS" width="1" height="1" border="0" alt="" />
{% endhighlight %}

   Note the link has a one-pixel image link Amazon uses to track the number of impressions.


If you would like to list products you make on Amazon,
   get an account Seller Account at <a target="_blank" href="https://sellercentral.amazon.com/gp/homepage.html">
   sellercentral.amazon.com/gp/homepage.html</a>.


### Google Affiliate Ads

Ideally, I would put a vertical ad under the table of contents.


## Site Search

A Node.js library to add search functionality to any Jekyll blog
<a target="_blank" href="http://christian.fei.ninja/Simple-Jekyll-Search/">Demo here</a>
is available
from <a target="_blank" href="https://github.com/christian-fei/Simple-Jekyll-Search">
this repo</a>.

Theme http://mmistakes.github.io/so-simple-theme/theme-setup/#jekyll-search
activates each page using it with the **search_omit: true** front matter.


## .gitignore

This list of folders and files is about what processing occurs locally.

{$ endhighlight text %}
_site
.sass-cache
.DS_Store
*.sublime-project
*.sublime-workspace
codekit-config.json
node_modules
_asset_bundler_cache
.jekyll-metadata
{$ endhighlight %}

## Additional features

[Make Jekyll multi-lingual](https://www.sylvaindurand.org/about/)


## Deploy to server

   * http://help.github.com/articles/using-jekyll-with-pages/

   * http://goo.gl/hE3Zj2 to
   http://nicolasgallager.com/simple-git-deployment-strategy-for-static sites/

   * jekyllrb.com/docs/deployment-methods/


## Questions

QUESTION: How to add regular .html files to the site.

TODO: Inspired by <a target="_blank" href="http://www.shamimeboodhoo.com/building-photomap/">
Shamime's photomap building</a>, I added a Photomap tab and folder on my site.


http://loyc.net/2014/javascript-toc.html

QUESTION: Spell checking in GitHub?

## Footnotes

* Tutorial: http://jekyll.tips/jekyll-casts/
