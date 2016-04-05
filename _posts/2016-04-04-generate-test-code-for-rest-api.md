---
layout: post
title: "Scala Programs Generate Test Code"
excerpt: "No waiting for test automation"
tags: [text to speech, JavaScript, programming]
image:
  feature: pic white robots woman 1900x500.jpg
  credit: Cyberconstruct.be
  creditlink: http://cyberconstruct.be/2015/02/digital-job-crafting/
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />
{% include _toc.html %}

I have a dream ...

where developers get their 
<a href="#TestScripts">test code</a> 
not by waiting for testers,
but by 

<img width="451" alt="fig test code gen" 
src="/images/fig test code gen 1480x838.png">

0. <a href="#TestCodeGener">test code generation programs</a> referencing

0. a <a href="#SpecDB">specification database</a>

0. also used to create client application programs,

0. all done by a <a href="#Toolchain">toolchain</a>
   of Continuous Integration/Continous Deployment.

0. The specifications can be specified manually or
   generated from programs which scan programming code
   to extract specifications.

0. Variations in the generated code
   are defined in a <a href="#GenControlFile">control file</a>.

0. This control file can be edited manually using a text editor
   and manually referencing the specifications,

0. adjusting for issues observed by the generator.

0. Results from test generator run include timings of transactions 
   and size of resources processed on the client 
   and

0. metrics from monitoring of servers.

0. Analysis of these results are made light of the 
   original specifications.

0. Insights from human or artificial intelligence 
   doing the analysis 
   would influence 
   what testing code to generate in subsequent rounds.

## What took us so long?

I think that when software vendors focus on tools for testers,
they may miss or dismiss the idea of eliminating them.

The automation discusseed here has the objective of "testers"
being developers themselves -- developers of test code generation programs.

The audience for this page are developers who want to move faster.

<a name="SpecDB"></a>

## Specification databases

Several databases have grown up over the years:

* <a href="#WADL">WADL</a>
* Swagger
* RAML
* DOORS requirements
* etc.

Specifications for REST API (such as Swagger)
   are more amenable as the basis for generating code
   if they are <strong>complete</strong> specifications of how
   client computers interact with servers.

   Specifications about screen elements may be too complex 
   or don't provide enough information for use in code generation
   at this point in time.


<a name="WADL-example"></a>

### WADL Example

Let's use the sample 
<a target="_blank" href="/assets/yahoo-news-call.wadl.xml">
yahoo-news-call.wadl.xml</a> file from the
Wikipedia page defining one.
Open the file using an XML reader app.

0. The service endpoint is specified by:

   <pre><code>
   &LT;resources base="http://api.search.yahoo.com/NewsSearchService/V1/"> 
   </code></pre>

<a name="TestScripts"></a>

## Test code

There are several languages used by test script processors:

   * XML for JMeter
   * <a href="#JavaSeleniumSample">Java for Selenium</a>
   * C for LoadRunner
   * <a href="#LRJS">JavaScript for LoadRunner</a>
   * VB for HP QTP
   * SOAPUI
   * many others

<a name="LRJS"></a>

### JavaScript LoadRunner Example

An example of the JavaScript code generated to 
emulate a client retrieving an index.html file:

{% highlight html %}
  web.url(
    {
      name : 'index.html', 
      url : '{pEndPoint}', 
      resource : 0, 
      recContentType : 'text/html', 
      referer : '', 
      snapshot : 't1.inf', 
      mode : 'HTML'
    }
  );
{% endhighlight %}

"{pEndPoint}" is the run parameter containing:

    http://api.search.yahoo.com/NewsSearchService/V1/

The "mode: HTML" specifies processing by LoadRunner to 
scan the html returned and issue requests for 
links to CSS, JavaScript, images, etc.

(Images specified within CSS are not retrieved this way)

<a name="JavaSeleniumSample"></a>

### Java Selenium Example

TODO:

<a name="GenControlFile"></a>

## Generator Control File

We use the <strong>yml format</strong> that can be read by humans and computers. Ruby programmers are used to such files.

Since Swagger users may prefer JSON formatting.

0. Input <a href="#SpecDB"> Specification database</a>

0. Output <a href="#TestScripts"> Test code language</a>

0. Authentication.

0. Call Method (GET, PUT, etc.).

0. Authorization (such as tokens in the HTTP header).

0. Response code (if not standard 200).

0. Reptitions.

0. Negative tests (to force 400 to return).

0. Data errors (bad attribute names, bad attribute value).

<a name="Toolchain"></a>

## CI/CD Toolchain


<a name="TestCodeGener"></a> 

## Test code generation programs

I have examples of code generation programs written in 
Python, PHP, Java, Scala, and even VBScript in Excel files.



