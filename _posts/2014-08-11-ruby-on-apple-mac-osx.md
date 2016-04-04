---
layout: post
title: "Ruby with RVM on Mac OSX"
excerpt: ""
tags: [ruby, apple, mac, setup, programming]
image:
  feature: pic ruby full 1900x500.jpg
  credit: Ruby Inside
  creditlink: http://www.rubyinside.com/advent2006/24-wallpapers.html
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


The Ruby language compiler is included in Mac OSX.

To see the current version number:

<pre><strong>
ruby --version
</strong></pre>

The response for the Yosemite default:

<tt>
ruby 2.0.0p481 (2014-05-08 revision 45883) [universal.x86_64-darwin14]
</tt>

After updating (below) on April 19, 2015:

<tt>
ruby 2.2.2p95 (2015-04-13 revision 50295) [x86_64-darwin14]
</tt>


### Get the current gem version number:

<pre><strong>
gem --version
</strong></pre>

The response for the Yosemite default:

<tt>
2.0.14
</tt>
After updating (below) on April 19, 2015:
<tt>
2.4.6
</tt>

### Update RubyGems and Bundler:

<pre><strong>
sudo gem update --system
</strong></pre>

The response:

<pre>
Password:
Updating rubygems-update
Fetching: rubygems-update-2.4.6.gem (100%)
Successfully installed rubygems-update-2.4.6
Parsing documentation for rubygems-update-2.4.6
Installing ri documentation for rubygems-update-2.4.6
Installing darkfish documentation for rubygems-update-2.4.6
Installing RubyGems 2.4.6
RubyGems 2.4.6 installed
Parsing documentation for rubygems-2.4.6
Installing ri documentation for rubygems-2.4.6
=== 2.4.6 / 2014-02-05

Bug fixes:
...

RubyGems installed the following executables:
/System/Library/Frameworks/Ruby.framework/Versions/2.0/usr/bin/gem

Ruby Interactive (ri) documentation was installed. ri is kind of like man
pages for ruby libraries. You may access it like this:
ri Classname
ri Classname.class_method
ri Classname#instance_method
If you do not wish to install this documentation in the future, use the
--no-document flag, or set it as the default in your ~/.gemrc file. See
'gem help env' for details.

RubyGems system software updated
</pre>


### Update Bundler:

<pre><strong>
sudo gem install --no-rdoc --no-ri bundler
</strong></pre>

The response:

<pre>
Fetching: bundler-1.9.4.gem (100%)
Successfully installed bundler-1.9.4
1 gem installed
</pre>


### Update gem:
<pre><strong>
sudo gem update
</strong></pre>

The response takes several minutes becuase it touches every gem:

<pre>
Updating installed gems
Updating CFPropertyList
</pre>

Press y and Enter if you see:

<pre>
rake's executable "rake" conflicts with /usr/bin/rake
rdoc's executable "rdoc" conflicts with /usr/bin/rdoc
rdoc's executable "ri" conflicts with /usr/bin/ri
</pre>


### Cleanup gem:

<pre><strong>
sudo gem cleanup
</strong></pre>


<a name="ruby-rvm"></a>

### Ruby Version Manager

To upgrade:

<pre><strong>
rvm get head
</strong></pre>

If the response is 
<tt>
-bash: rvm: command not found
</tt>

Have the rvm shell configuration loaded:

<pre><strong>
source ~/.rvm/scripts/rvm
type rvm | head -n 1
</strong></pre>

The response should be:

<tt>
rvm is a function
</tt>
Try rvm get head again.



### To upgrade:

<pre><strong>
rvm autolibs homebrew
rvm install ruby
</strong></pre>


To install the latest stable release:

<pre><strong>
\curl -ssL https://get.rvm.io | bash -s stable
</strong></pre>

The response:

<pre>
Downloading https://github.com/rvm/rvm/archive/1.26.11.tar.gz
Downloading https://github.com/rvm/rvm/releases/download/1.26.11/1.26.11.tar.gz.asc
Found PGP signature at: 'https://github.com/rvm/rvm/releases/download/1.26.11/1.26.11.tar.gz.asc',
but no GPG software exists to validate it, skipping.

Installing RVM to /Users/wilsonmar/.rvm/
Adding rvm PATH line to /Users/wilsonmar/.profile /Users/wilsonmar/.mkshrc /Users/wilsonmar/.bashrc /Users/wilsonmar/.zshrc.
Adding rvm loading line to /Users/wilsonmar/.profile /Users/wilsonmar/.bash_profile /Users/wilsonmar/.zlogin.
Installation of RVM in /Users/wilsonmar/.rvm/ is almost complete:

* To start using RVM you need to run `source /Users/wilsonmar/.rvm/scripts/rvm`
in all your open shell windows, in rare cases you need to reopen all shell windows.

# Wilson Mar,
#
#   Thank you for using RVM!
#   We sincerely hope that RVM helps to make your life easier and more enjoyable!!!
#
# ~Wayne, Michal & team.

In case of problems: http://rvm.io/help and https://twitter.com/rvm_io

* WARNING: You have '~/.profile' file, you might want to load it,
to do that add the following line to '/Users/wilsonmar/.bash_profile':

source ~/.profile
</pre>


Some say at this point close the terminal and open again.


This also provides instructions on installation of Ruby:

http://www.createdbypete.com/articles/ruby-on-rails-development-setup-for-mac-osx/


## More on OSX

This is one of a series on Mac OSX:

{% include mac_links.html %}
