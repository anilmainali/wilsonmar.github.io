---
layout: post
title: "Markdown readers and hosting"
excerpt: "Take the easy way or the flexible way"
modified:
tags: []
image:
  feature: pic rainbow splash black apple logo 1900x500.jpg
  credit: Brothersoft
  creditlink: http://m.img.brothersoft.com/android/a0/a054685c75c309c2b6dfd3c96972dded_screeshots_3.jpeg
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

The diagrams below are animated in PowerPoint and go with a narrative to each step.
I then created a screencast video of it.
And a step-by-step hands-on tutorial to explain each step.

## Playlist
You will prefer accessing the videos via this playlist:

> <a target="_blank" href="https://goo.gl/12C1BF">https://goo.gl/12C1BF</a>

A playlist link lists the latest versions because individual videos can be added or removed.

Direct links to individual YouTube videos can become stale when newer versions are downloaded.

## Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/ub2DFbn16zg" frameborder="0" allowfullscreen></iframe>

## Narration

### Markdown editors
The HTML displayed on browsers is generated from markdown text that's easier to write than HTML tags. 

Behind the scenes, the service that generates the HTML is called Jekyll and it uses the Kramdown parser.

GitHub's on-line text editor shows both raw markdown and HTML generated from it. Because GitHub provides an applications programming interface, several alternatives to GitHub’s online text editor have been created.

The dillenger online editor does what the GitHub editor does, 
but can also store files in Google Drive and Dropbox.

The stackedit browser app does all that and stores markdown files within the browser for temporary offline edits.

There are also mobile apps that display content from GitHub.

If you name a repository with your account name followed by .github.io, 
with markdown text in its master branch, GitHub will automatically 
generate HTML and serve them to vistors.

Markdown in additional repositories under the same account
can appear as projects under the account's github.io domain 
if they are in a orphan branch named gh-pages.

### Wiki GitHub
Markdown text can also be written in a wiki that can be created alongside each repo to present documentation associated with programming code.

In its wiki, GitHub can render alternative markdown flavors such as .asciidoc and others.

Unlike code in GitHub, GitHub’s wiki does not (currently) accept pull requests from strangers. 
One now has to be named a member or contributor to change wiki contents.

However, there is a 3rd-party who runs a ghw node.js app to generate wiki markup into gh-pages.

### Offline
For those who want to browse and edit markdown offline, a git client from several publishers can be used to transfer files from GitHub.com or other cloud repository.

The multi-platform and multi-lingual client program Haroopad (http://pad.haroopress.com/user.html#download) and mou both display two panes on their program so that markdown text is edited on the left pane while the formatted display is shown on the right pane.

But for high quality display of HTML with markdown, many prefer to use their own favorite text editor, then display markdown locally using the open-source Python web server called 
Grip (https://github.com.com/joeyespo/grip). 
It uses the rendering API provided by GitHub to format markdown into HTML for display. Grip developers are working on an internal renderer for offline use. 

Although Grip can also generate HTML for transfer to a custom web server for public access,
the most accurate way to create HTML from markdown is running Jekyll under Ruby and other gems.
The resulting files can be pushed back to GitHub or the generated _sitse files can be sent to
3rd-party hosting services
such as Heroku or specialized hosting services such as 
gitbook.com, leapub.com, and others. Leanpub can also receive files via Dropbox. 

### Alternative formats
Work reformatting and transferring to a web host may be automated on the server as part of a Continuous Integration toolchain. 

Many prefer hosting where they can render not just HTML, but epub files for Apple mobile devices, pdf files, and mobi files for display on Amazon Kindle tablets. AZW is Amazon’s proprietary format to support Digital rights Management.

Another popular approach to generate HTML is to use Jekyll plus other Ruby gems and custom templates. 

Included with 3rd-party hosting may be a CDN (Content Delivery Network) such as what Amazon, Google, and others provide to scatter files all over the world for faster access.

