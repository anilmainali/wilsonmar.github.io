---
layout: post
title: "JavaScript in LoadRunner"
excerpt: "Sample code and tutorial here"
tags: [JavaScript, Load Testing, LoadRunner]
author: anil_mainali
image:
  feature: pic brown running horses 1900x500.jpg
  credit: Steve Mckinzie
  creditlink: 
comments: true
---
<i>{{ page.excerpt }}</i>
<hr />

{% include _toc.html %}


JavaScript is popular now.

This is one of a series on how LoadRunner has embraced JavaScript:

1. <a href="#TruClient">Create TruClient script with JavaScript</a>.

2. <a href="#LRCJS">Call JavaScript within a LoadRunner C-language script</a>. 

3. <a href="#LRJS">Scripting in JavaScript language</a> (instead of C or Java).

Here are examples of each.


<a name="TruClient"></a>

## Create TruClient scripts with JavaScript

Download Zip of the <strong>UISamples</strong> TruClient script repository at:

   <a target="_blank" href="https://github.com/TruClient/UISamples">
   https://github.com/TruClient/UISamples</a>

There are several TruClient scripts there, each in a separate folder.

The HP example shows a website that can only be load tested using TruClient (not C programming).

I created a whole 2-day hands-on class explaning these.

> Call me to get up and running on TruClient quickly.


<a name="LRCJS"></a>

## Call JavaScript within a LoadRunner C-language script 

A tutorial on how you can create and use a JavaScript file within a LoadRunner C-language script
(using Agile principles) is in the README.md file within the the
<strong>random_birthdate_js</strong> folder at:

   <a target="_blank" href="https://github.com/wilsonmar/LoadRunner/tree/master/random_birthdate_js">
   https://github.com/wilsonmar/LoadRunner/tree/master/random_birthdate_js</a>

Download a Zip the whole set of LoadRunner sample scripts from:

   <a target="_blank" href="https://github.com/wilsonmar/LoadRunner">
   https://github.com/wilsonmar/LoadRunner</a>

If you have a Git client, clone the set of LoadRunner sample scripts using command:

   <a target="_blank" href="https://github.com/wilsonmar/LoadRunner">
   git clone https://github.com/wilsonmar/LoadRunner.git</a>


> Call me to get good at JavaScript without wasting a lot of time.


<a href="#LRJS"></a>

## Script in JavaScript language

To use VuGen to generate a LoadRunner script in JavaScript: 

1. Create a File as protocol <strong>Web HTTP/HTML</strong>.

2. Switch to Windows Explorer to see that Action.js was created rather than Action.c.
   Then switch back to VuGen.

3. In menu Record > Recording Options > Script, click the drop-down for Scripting Language 
   to change from C to JavaScript.

4. Have a ThinkTime function generated on every request.

   In General: Script, to the right of
   "Generate think time greater than threshold",
   double-click on the number (default 3) and change it to 0.

5. Make a recording using WebTours (after starting it).

6. Login as "jojo" with password "bean".
   Click Flights.
   In "Find Flights", click "Sign Off", then Stop recording.

What follows is a hands-on tutorial to show you the most important edits to make to LoadRunner scripts. 

> I write programs that makes these edits for you. Call me!


### Adjust link retrieval mode 

A request generated looks like this:

{% highlight html %}
web.url(
{
    name : 'index.htm', 
    url : 'http://127.0.0.1:1080/WebTours/index.htm', 
    targetFrame : '', 
    resource : 0, 
    recContentType : 'text/html', 
    referer : '', 
    snapshot : 't1.inf', 
    mode : 'HTML'
}
);
{% endhighlight %}

A value in referer is not needed because the Web Tours sample application does not use it.

NOTE: The `mode: HTML` activates a feature of LoadRunner which 
scans the html returned and issue requests for 
links to CSS, JavaScript, images, etc.

(Images specified within CSS are not retrieved this way)

CHALLENGE: Change to `mode: HTTP` for LoadRunner to NOT request links as well.
Generate just individual resource requests during recording by setting:

   <img src="/images/LR1250 Recording Recording option 1034x204.png">

Run the generated script.


### Add a Parameter to make GET call 

Parametize JavaScript code generated to 
emulate a client retrieving an index.html file:

{% highlight html %}
var pEndPoint = 'http://api.search.yahoo.com/NewsSearchService/V1/';
{% endhighlight %}

`{pEndPoint}` is a run parameter which can be changed to:

    http://api.search.yahoo.com/NewsSearchService/V1/


### Verify response

How do you know whether the correct screen was returned?

Add code to scan the stream after receipt to identify a string of text:

{% highlight html %}
web.regFind(
{
   text : 'Find Flight', 
   search : 'Body'
}
);
{% endhighlight %}

Run the script both ways so you see the output either way.

NOTE: An error is raised immediately if the text is not found,
but at where the request is made, not at this script line 
which registers the capture during request execution.


### Register Find String after download

Add a foundcount to the call:

{% highlight html %}
web.regFind(
{
    text : 'Find Flight', 
    foundcount : departDate_isfound,
    search : 'Body'
}
);
{% endhighlight %}

CHALLENGE: Look at the Help screen for the function to come up with a way to  
fail if the text is found (such as an error message).


### Control whether to stop on error

Some test run scenarios do not want to end if an error occurs,
so use a variable named rc (return code) 
when returning control up the call hierarchy rather than stopping: 

{% highlight html %}
var rc=0;
rc = web.image(
{
    name : 'Search Flights Button', 
    alt : 'Search Flights Button', 
    snapshot : 't3.inf'
}
);
if( rc != 0 ){
   lr.outputMessage(">> ERROR Logged-in=" + lr.evalString( "{UserIds_userid}" ));
   // Handle error here:
   return rc;  // 
}else{
   lr.outputMessage(">> Logged-in=" + lr.evalString( "{UserIds_userid}" ));
}
{% endhighlight %}


The variable rc (return code) is set at the front of the function  
so the function can return a status.

Unlike C, there is no LR_PASS in JavaScript, so we need to use 0.

### OutputMessage

{% highlight html %}
lr.outputMessage(">> Logged-in=" + lr.evalString( "{UserIds_userid}" ));
{% endhighlight %}

PROTIP: Specify a special set of characters at the front of output messages
so they are easy to identify among potentially many output lines.

CHALLENGE: Look in Help for other types of messages.


### Use generic functions

Replace the function with a call to a generic function
such as:

{% highlight html %}
var rc=0;
    rc = wi.web.image( "Search Flights Button", "Search Flights Button" );
if( rc != 0 ){
    lr.outputMessage(">> ERROR Logged-in=" + lr.evalString( "{UserIds_userid}" ));
    // Handle error here.
    return rc;
}else{
    lr.outputMessage(">> Logged-in=" + lr.evalString( "{UserIds_userid}" ));
}
{% endhighlight %}


The function above is defined within 
<strong>wi.utilities.js</strong> in GitHub:

{% highlight html %}
function wi.web.image( in_name, in_alt )
{
   var rc=0;
   rc = web.image( in_name, in_alt )
   {
      name : _in_name, 
      alt : _in_alt, 
      snapshot : 't3.inf'
   }
   return rc;
);
{% endhighlight %}

PROTIP: Do not use generic functions to output messages. 


### Capture Parameter Extended

To have LoadRunner count the number of times it finds text in the input stream:

{% highlight html %}
web.regSaveParamEx(
{
    paramName : 'departDate', 
    lb : 'name=\"departDate\" value=\"', 
    rb : '\"', 
    scope : 'Body', 
    requestUrl : '*/reservations.pl*'
}
);
{% endhighlight %}

The code to take action depending on what is in the variable updated. 

NOTE: LoadRunner automatically creates the paramName parameter
specified.


<hr />

### Generic Start and End Transaction Functions

PROTIP: Replace think-time functions with a generic function:

   wi.StartTrans( pCurrentTrans, in_rc );

Add a call to end transaction:

   rc = wi.EndTrans( pCurrentTrans, in_rc );



### Start and End Transaction Names

PROTIP: Specify Start and End transactions using a parameter
so the code is more easily pastable and there is no danger of typos,
avoiding the most common cause of runs being aborted.

{% highlight html %}
var pCurrentTrans = 'WT3_T22_Travel_Search_Flight';

lr.startTransaction(pCurrentTrans);

...

lr.endTransaction({pCurrentTrans}, lr.AUTO);
{% endhighlight %}

Parametizing transaction names is needed to make generic functions
that reduce the amount of coding. The less coding lines, the smaller the script's memory footprint.
Smaller scripts allow for more Vusers to fit into available memory on load generator machines.

PROTIP: Start transaction immediately before web request functions
to avoid having data preparating time be counted in the transaction time.


<hr />

### Get Image by Screen Name

LoadRunner can generate script code like this based on the text of the link
(rather than the URL of the link):

{% highlight html %}
web.image(
{
name : 'Search Flights Button', 
alt : 'Search Flights Button', 
snapshot : 't3.inf'
}
);
{% endhighlight %}



### Submit form to Sign-up

To submit an HTML form:

{% highlight html %}
web.submitForm(
{
name : 'login.pl_2', 
snapshot : 't11.inf', 
itemData :  [
{name : 'username', value : '{UserIds_userid}'},
{name : 'password', value : '{UserIds_pwd}'},
{name : 'passwordConfirm', value : '{UserIds_pwd}'},
{name : 'firstName', value : ''},
{name : 'lastName', value : ''},
{name : 'address1', value : ''},
{name : 'address2', value : ''},
{name : 'register.x', value : '53'},
{name : 'register.y', value : '3'}
]
}
);
{% endhighlight %}

Some of the fields, such as register.x, can be marked hidden within the form
captured by LoadRunner.

### Submit data to POST Sign-in

{% highlight html %}
web.submitData(
{
name : 'login.pl', 
action : '{pProtocolHostPort}/cgi-bin/login.pl', 
method : 'POST', 
recContentType : 'text/html', 
referer : '{pProtocolHostPort}/cgi-bin/nav.pl?in=home', 
snapshot : 't2.inf', 
mode : 'HTML', 
itemData : 
[
{ name : 'userSession', value : '{userSession}' }, 
{ name : 'username', value : '{UserIds_userid}' }, 
{ name : 'password', value : '{UserIds_pwd}' }, 
{ name : 'JSFormSubmit', value : 'on' }, 
{ name : 'login.x', value : '42' }, 
{ name : 'login.y', value : '8' }
]
}
);
{% endhighlight %}



## Resources to Learn JavaScript

There are many tutorials which teach JavaScript string manipulation and other topics:

* <a target="_blank" href="http://freecodecamp.com">freecodecamp.com</a>
  has learners use tutorials on codeacademy.com and other sites, then adds
  quizzes, all for free.

