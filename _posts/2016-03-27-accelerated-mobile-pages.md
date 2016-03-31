---
layout: post
title: "Accelerated Mobile Pages"
excerpt: "Faster is better!"
tags: [google, programming, sample, gist]
image:
  feature: pic brown blowholes sunset 1900x500.jpg
  credit: 
  creditlink: 
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}

PROTIP: A recent innovation (from the geniuses at Google) enables websites to load nearly instantly even on mobile devices with slow connections.

## Official sites about AMP

   * <a target="_blank" rel="amphtml" href="https://github.com/ampproject/amphtml">
   github.com/amphtml</a> is the technical home for source.

   * <a target="_blank" rel="amphtml" href="https://www.ampproject.org/">
   ampproject.org</a> is the marketing home.

   * <a target="_blank" rel="amphtml" href="https://www.ampproject.org/docs/get_started/about-amp.html">
   ampproject.org/docs</a>

   * <a target="_blank" rel="amphtml" href="https://www.youtube.com/watch?v=iZZdhTUP5qg">
   Google I/O 2015 - The next generation mobile web</a>

The rest of this section describes its use.

## Marvel at the speed of AMP

See how fast the Jekyll theme's demo website (by Adam Geitgey) renders:

   * <a target="_blank" rel="amphtml" href="http://ageitgey.github.io/amplify/2016/03/08/example-post.html">
   http://ageitgey.github.io/amplify/2016/03/08/example-post.html</a>

See even faster rendering on Google's CDN (Content Delivery Network):

   * <a target="_blank" rel="amphtml" href="https://amp.gstatic.com/c/s/ageitgey.github.io/amplify/2016/03/08/example-post.html">
   https://<strong>amp.gstatic.com</strong>/c/s/ageitgey.github.io/amplify/2016/03/08/example-post.html</a>

or

   * <a target="_blank" rel="amphtml" href="https://cdn.ampproject.org/c/s/ageitgey.github.io/amplify/2016/03/08/example-post.html">
   https://cdn.ampproject.org/c/s/ageitgey.github.io/amplify/2016/03/08/example-post.html</a>

See Google's search demo featuring the AMP carousel:

   * <a target="_blank" rel="amphtml" href="http://g.co/ampdemo">
   g.co/ampdemo</a>

   * <a target="_blank" rel="amphtml" href="https://www.youtube.com/watch?v=3dGO0Vs3ORg">
   A video showing its speed on mobile</a>


## Videos about AMP

Paul Bakaus, Developer Advocate has two videos:

   {% include youtube-amp-video-01.html %}

   Also:

   {% include youtube-amp-video-02.html %}

&nbsp;

BTW, the above videos were served using AMP on this Jekyll-based site.


## How I added AMP to my Jekyll-based site

PROTIP: You don't need to have the whole site under AMP. 
Add the JavaScriipt to use AMP when you can.

### Add JavaScript libraries

1.  Add in the <HEAD> section this:
(In a Jekyll site, edit the <strong>_head.html</strong> within the <strong>_includes</strong> folder.)

    <pre><cone>
    &LT;script async custom-element="amp-youtube" 
    src="https://cdn.ampproject.org/v0/amp-youtube-0.1.js">
    &LT;/script>
    </code></pre>

2.  Add this above the ending </HEAD> tag:

    <pre><code>
    &LT;script async src="https://cdn.ampproject.org/v0.js">&LT;/script>
    </code></pre>

Yes, these really should be under the fold, but that's what Google does.

### Use amp-youtube> tags

Instead of this:

    https://www.youtube.com/watch?v=lBTCB7yLs8Y &LT;

Use this:

   <pre><code>
   &LT;amp-youtube data-videoid="lBTCB7yLs8Y" 
   layout="responsive" width="480" height="270">
   &LT;/amp-youtube>
   </code></pre>

   To get around in Markdown, 
   put the above in a <strong>amp-video.html</strong> file
   within the <strong>_includes</strong> folder,
   then use a Liquid include tag referencing that file:

   <pre><code>
   &#123;% include youtube-amp-video-01.html %}
   </code></pre>

## WordPress Plug-ins

   * <a target="_blank" rel="amphtml" href="https://github.com/Automattic/amp-wp/">
   https://github.com/Automattic/amp-wp</a> is officially supported.

   * <a target="_blank" rel="amphtml" href="https://wordpress.org/plugins/amp/">
   https://wordpress.org/plugins/amp/</a>

## Jekyll sites to use AMP

> If you see more, please let us know!

   * <a target="_blank" rel="amphtml" href="https://www.ampproject.org/docs/get_started/create_page.html"> 
   Create Your First AMP Page</a> 

   * <a target="_blank" rel="amphtml" href="http://fossbytes.com/google-amp-powered-jekyll-website-loads-faster/">fossbytes.com/google-amp-powered-jekyll-website-loads-faster</a>


### Get a sample Jekyll AMP site

0. Clone a AMP-enabled Jekyll theme from:
   
   * <a target="_blank" rel="amphtml" href="https://github.com/ageitgey/amplify">
   https://github.com/ageitgey/amplify</a>

   &nbsp;
   
0. Obtain dependencies:

   ```
   bundle
   ```

   The response on March 30, 2016:

   <pre>
Fetching gem metadata from https://rubygems.org/............
Fetching version metadata from https://rubygems.org/...
Fetching dependency metadata from https://rubygems.org/..
   </pre>
   <pre>
Gem::RemoteFetcher::UnknownHostError: no such name (https://rubygems.org/gems/hitimes-1.2.2.gem)
Using colorator 0.1
Using ffi 1.9.10
Installing sass 3.4.15
Installing rb-fsevent 0.9.5
Using kramdown 1.9.0
Using liquid 3.0.6
Using mercenary 0.3.5
Using rouge 1.10.1
Using safe_yaml 1.0.4
Using jekyll-paginate 1.1.0
Using bundler 1.11.2
An error occurred while installing hitimes (1.2.2), and Bundler cannot continue.
Make sure that `gem install hitimes -v '1.2.2'` succeeds before bundling.
   </pre>

0. Fix the dependency error 
   for those using Jekyll 3.0.

    ```
    gem install hitimes -v '1.2.2'
    ```

    Then try bundle again.

4.  Build the site:

    ```
    jekyll serve
    ```

    I get these errors:

    {% highlight text %}
    WARN: Unresolved specs during Gem::Specification.reset:
      jekyll-watch (~> 1.1)
    WARN: Clearing out unresolved specs.
    Please report a bug if this causes problems.
    Configuration file: /Users/mac/gits/jekyll/amplify/_config.yml

    Dependency Error: Yikes! It looks like you don't have jekyll-paginate or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. The full error message from Ruby is: 'cannot load such file -- jekyll-paginate' If you run into trouble, you can find helpful resources at 
    http://jekyllrb.com/help/! 
    jekyll 3.1.2 | Error:  jekyll-paginate
    {% endhighlight %}

5.  So I install the package even though GitHub has decided to not use it:

    ```
    gem install jekyll-watch -v 1.1
    ```

    The response:

    <pre>
    Successfully installed jekyll-watch-1.3.1
    Parsing documentation for jekyll-watch-1.3.1
    Done installing documentation for jekyll-watch after 0 seconds
    1 gem installed
    </pre>

    And:

    ```
    gem install jekyll-paginate
    ```

    The response:

    <pre>
    Successfully installed jekyll-paginate-1.1.0
    Parsing documentation for jekyll-paginate-1.1.0
    Done installing documentation for jekyll-paginate after 0 seconds
    1 gem installed
    </pre>

0.  Try again:

    ```
    jekyll serve
    ```

    The response:

    <pre>
    </pre>

## View Generated Site

6.  In a browser, view the site in validation mode:

    ```
    localhost://4000
    ```



### AMP Validator

5.  In a browser, view the site in validation mode:

    ```
    localhost://4000#development=1
    ```


   * <a target="_blank" rel="amphtml" href="https://www.ampproject.org/docs/guides/validate.html"> https://www.ampproject.org/docs/guides/validate.html</a>

   Examples include:
   
   + no scrollng elements
   + no stylesheets over 50K


### Add NewsArticle for better search positioning

PROTIP: Google gives preferential treatment to AMP pages on Mobile Search.

To get featured on Google search results, the `_includes/metadata.json` file 
provides the NewsArticle file Google uses. See:

   * <a target="_blank" rel="amphtml" href="http://schema.org/">
   http://schema.org/</a>


### Convert SCSS to CSS

With AMP, all CSS must be inline (no external CSS files) within a <style amp-custom> in the header. Because of this, the main css file for this site is in _includes/styles.scss (instead of the standard css/ folder) and in-lined into the header of every page via the special scssify filter in _includes/head.html.

CAUTION: The AMP specification forbids the use of some CSS selectors and attributes. Because of this, it is not a good idea to include the main stylesheet by default.

1.  Copy from within folder css file main.scss.

2.  Open folder _includes to paste in file styles.scss.

3.  Rename file name main.scss to styles.scss.

4.  Edit folder _includes file head.htm to define the include:

   <pre></code>
   &#123;% include styles.scss %}
   </code></pre>

5.  Paste in the target page between style tags.

6.  Ensure the page still renders correctly.

### Add rel="amphtml" to href links

In order to do DNS pre-connects for faster speed, AMP needs an extra attribute in links to make links discoverable by the Google search engine. This makes it happen on existing Jekyll templates:

1.  Get the rb files local:
   
    ```
    git clone https://github.com/juusaw/amp-jekyll
    ```

2.  Copy in folder _plugins the ruby files from the repo: 

    ```
    amp_generate.rb and amp_filter.rb.
    ```

3.  Copy into the _layouts folder file amp.html from the repo.

4.  Install for HTML parsing:

    ```
    gem install nokogiri
    ```

5.  Install for image processing:

    ```
    gem install fastimage
    ```

6.  Add this to post headers:

   <pre></code>
   &#123;% if page.path contains '_posts' %}
   &LT;link rel="amphtml" href="{{ page.id | append:'/index.html' | prepend: site.baseurl | prepend: site.url }}">
   &#123;% endif %}
   </code></pre>

Add rel="canonical" to regular href links

### Use <amp-ad> for advertisements

AMP enables lazy-load of and prioritization of ads identified like this:

   <pre><code>
   &LT;amp-ad width=300 height=250 type="a9"
   data-axx_size="300x250"
   data-axx_pubname="test1"
   data-aax_src="302">
   &LT;/amp-ad>
   </code></pre>

Ad Platforms integrated into AMP

   * AdSense by Google
   * A9 by Amazon
   * DoubleClick
   * Ad Reactor
   * Ad Tech by AOL

### Use &LT;amp-img> instead of &LT;img> tags

AMP gets some of its speed from caching images and video. It needs special tags with both a height and width specified. Examples:


    <pre><code>
    <amp-img media="(min-width: 650px)" width="600" height="300" 
    layout="responsive" src="/assets/images/your_picture.jpg"></amp-img>
    </code></pre>

(Replace src contents with your own)

## Add other extended AMP tags 

They are described at:

   * <a target="_blank" rel="amphtml" href="https://github.com/ampproject/amphtml/blob/master/extensions/README.md">
   https://github.com/ampproject/amphtml/blob/master/extensions/README.md</a>

NOTE: AMP implements RAIL.

   * <a target="_blank" rel="amphtml" href="https://www.youtube.com/watch?v=X-qZu2Aoo98">
   AMP implements RAIL</a>


### Add NewsArticle for better search positioning

The AMP Project provides helpers for many other types of content like audio, ads, Google Analytics, etc. Built-in AMP tags are described at: 

   * <a target="_blank" rel="amphtml" href="https://github.com/ampproject/amphtml/blob/master/builtins/README.md">
   https://github.com/ampproject/amphtml/blob/master/builtins/README.md</a>


## More videos

   * <a target="_blank" rel="amphtml" href="https://stackoverflow.com/questions/tagged/amp-html"> amp-html on stackoverflow</a>

   * <a target="_blank" rel="amphtml" href="https://www.youtube.com/watch?v=-zSkahXzAZI">
   Duda Webinar - What is the Google AMP Project?</a>
   discussion among developers.

## Opinion about implementing AMP

   * <a target="_blank" rel="amphtml" href="https://www.tunetheweb.com/blog/implementing-accelerated-mobile-pages/">
   tunetheweb.com/blog/implementing-accelerated-mobile-pages</a>

## AMP Implements RAIL

   * Paul Irish