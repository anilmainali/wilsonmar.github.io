---
layout: post
title: "Text Editors on Mac OSX"
excerpt: "One second saved per minute = 1.666% better living"
tags: [apple, mac, setup]
image:
  feature: pic RichTextEditorToolBar 1900x500.jpg
  credit: MH Education
  creditlink: http://highered.mheducation.com/sites/0000065899/student_view0/question_editor/rich_text_editor_toolbar.html
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

There is not shortage to the number of programs available to edit code.

Free:

   * Atom from GitHub (free)
   * Microsoft Code (free)

Licensed:

   * <a href="#SublimeTextz">Sublime Text</a> : $89 nagware
   * Notepad++ (on Windows)

IDEs:

   * IntelliJ from JetBrains
   * Visual Studio from Microsoft


<a id="SublimeTextz"></a>

## Sublime Text Text Editor 

Use the Sublime Text 2 text editor from the command line,
make a symlink to subl. 
Assuming you've placed Sublime Text 2 in the Applications folder, and that you have a ~/bin directory in your path, run:

<tt><strong>
sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
</strong></tt>

Use the Sublime text editor to open the profile file:
<strong>subl .bash_profile</strong>

Alternately, use the editor built into a Mac:
<strong>vim .bash_profile</strong>

To get out of VIM, type: 

<pre>
:q to quit (short for :quit)
:q! to quit without saving (short for :quit!)
:wq to write and quit (think write and quit)
:x to write and quit (shorter than :wq)
:qa to quit all (short for :quitall)
</pre>


To use Sublime Text 2 as the editor for many commands that prompt for input, set your EDITOR environment variable:

<pre>
export EDITOR='subl -w'
</pre>
Specifying -w will cause the subl command to not exit until the file is closed.



<a id="Git_Editor"></a>

## Git Editor


If Git finds conflicts, it needs a way to show the differences in a text editor.

Git uses the default vim editor.
To quit the page, press <strong>:q!</strong> (colon to specify a command, q to specify quit, exclaimation point for immediate).

Sublime Text is a popular text editor.

https://help.github.com/articles/associating-text-editors-with-git/




<a id="IntelliJ"></a>

## IntelliJ Control Key Shortcuts


During initial configuration, specify the Project SDK
using the command up-arrow to the secret portal:

<ol type="1">
<li> Click New button </li>
<li> Select JDK </li>
<li> Click on the folder list (containing bin, etc.)</li>
<li> Press <strong> command + up arrow </strong>
to <strong> navigate up a folder level</strong>
from Home to the **MacOS** folder. </li>
<li> Click Choose to select the Java associated
with the system. This is called the "Secret Portal" approach.</li>
</ol>

Defaults changeable in Preferences | Keymaps

command + G to Generate
<br />
command + O to go to class
<br />
command + &#9003; Delete line

http://symbolcodes.tlt.psu.edu/keyboards/charpalosx.html 




<a id="Compare_Git"></a>

## Compare Lines within Git

Set colors in diff output globally across all projects:

<pre>
git config --global color.ui  auto
</pre>	

Get commit id's from a list of recent commits:

<pre>
git log
</pre>

For more lines, press Enter or down arrow until you reach (END).<br />
To stop viewing the log, press q (for quit).


For a difference between content associated with commit ids:

<pre>
git diff  id1   id2
</pre>


<a id="Grepz"></a>

## Grep Utilities

My version of the Grep utility that filters what is piped into it:

<tt><strong>grep --version</strong></tt>
is
<tt>grep (BSD grep) 2.5.1-FreeBSD</tt>

Grep filters what is piped into it.


## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
