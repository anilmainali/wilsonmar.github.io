---
layout: post
title: "Static websites"
excerpt: "Version controlled simplicity"
tags: [website, builder, simplicity, jekyll]
image:
  feature: pic white hand key ownership 1900x500.jpg
  credit:
  creditlink:
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

## Static is Cool Now
Here is why building a static site is now "cool".

First of all, static sites are the fastest possible.
This is for two reasons.

1. Static site HTML files can reside in CDN (Content Distribution Networks) scattered throughout the world, which reduces network latency.

2. There is no time lost generating HTML dynamically.
CMS (Content Management Systems) such as WordPress
make calls to a single-threaded database, which adds time.

Secondarily, the rise of APIs has removed many of the limitations
of static HTML.

## Tools to generate static websites
I've configured a few, but most recently:

   * <strong>[Jekyll](/jekyll-site-development)</strong> is the most popular among static website generation tools largely because GitHub.io websites are
   hosted automatically, and free, from repositories in GitHub.com.

   Much like what wordpress.org provides, but
   with the git version control added -- a crucial feature.

Surveys are:

   * <a target="_blank" href="http://www.staticgen.com/">staticgen.com</a>
   presents its list in a gallery.

   * <a target="_blank" href="https://staticapps.org/">staticapps.org</a>

   * <a target="_blank" href="https://staticsitegenerators.net/">staticsitegenerators.net</a>
   presents an exhaustive list.

## Sites using this approach

* <a target="_blank" href="http://myers.io/posts/">myers.io/posts</a>

## There is a downside
Some feel git is a hassle to use.

Some prefer the WSIWYG editors like Microsoft Word
over text editors and writing markdown code.

## Footnotes
People who have commented on this include:

* <a target="_blank" href="http://www.shamimeboodhoo.com/from-wordpress-to-jekyll-and-a-new-design/">
  shamimeboodhoo.com/from-wordpress-to-jekyll-and-a-new-design</a>
