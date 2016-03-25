---
layout: post
title: "Write GitHub markdown text from HTML"
excerpt: "Syntax "
tags: [HTML, personalization, jekyll]
image:
  feature: pic rainbow splash black apple logo 1900x500.jpg
  credit: Brothersoft
  creditlink: http://m.img.brothersoft.com/android/a0/a054685c75c309c2b6dfd3c96972dded_screeshots_3.jpeg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

This post is about converting exsiting HTML into markdown text.

I wrote this because I haven't seen an approach like this.

And I have to convert hundreds of pages I've written in HTML since the 90's.


## History

GitHub uses

In March, 2016 GitHub began using the Kramdown

## Paragraphs

They say Markdown text is easier to write than HTML.

   * No need for `<p>` to force a blank line. Just a blank line will do.

    But avoid doing a mass change of `<p>` 

## Lists

CAUTION: Even though HTML can be written or pasted into markdown (.md) files,
HTML must be more correct than HTML read by internet browsers.

* There must be a blank line before `<ul>` or `<ol>`.

* For every `<li>` there needs to be a `</li>` or the rendering goes wacky.

* There must be a blank line after anchor tags `<a name=...` and a heading text line.

## Headings

Instead of the opening `<h2>` and such tags, replace with `##`.

The ending '##' character is optional. It can be any number of characters.

## Links

Markdown text is different than HTML in several ways:

* No need use HTML. However, to get links to open on a new window 
  (rather than let the new page hijack user attention),
  continue to use `<a taget="_blank' href=`.

* There must be at least one space between `<div>` and `</div>` tags.


## Liquid Markdown Syntax

* https://docs.shopify.com/themes/liquid/basics





