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


JavaScript is popular.

Although still capable, LoadRunner's days as a Windows desktop program.

Attention has been moving to the cloud.

There are several ways HP has embraced JavaScript:

1. <a href="#TruClient">TruClient makes use of JavaScript</a>.

2. <a href="#LRCJS">Call JavaScript from within a LoadRunner C-language script</a>. 

3. <a href="#LRJS">Scripting in JavaScript</a> (instead of C or Java).

Here are examples of each.


<a name="TruClient"></a>

## TruClient makes use of JavaScript

Download Zip of the <strong>UISamples</strong> folder at:

   <a target="_blank" href="https://github.com/TruClient/UISamples">
   https://github.com/TruClient/UISamples</a>

There are several TruClient scripts there, each in a separate folder.

The HP example shows a website that can only be load tested using TruClient (not C programming).

I created a whole 2-day hands-on class explaning these.

> Call me to get up and running on TruClient quickly.


<a name="LRCJS"></a>

## Call JavaScript from within a LoadRunner C-language script 

Download a Zip of the <strong>random_birthdate_js</strong> folder at:

   <a target="_blank" href="https://github.com/wilsonmar/LoadRunner/tree/master/random_birthdate_js">
   https://github.com/wilsonmar/LoadRunner/tree/master/random_birthdate_js</a>

The README.md file contains the tutorial on how you can create the script on your own,
using Agile principles.

> Call me to get good at this without wasting a lot of time.


<a href="#LRJS"></a>

## Scripting in JavaScript

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

## GET call

An example of the JavaScript code generated to 
emulate a client retrieving an index.html file:

{% highlight html %}
var pEndPoint = 'http://localhost:1080/CGI-BIN//login.pl?username=&password=&getInfo=true';
web.url(
{
    name : 'login.pl', 
    url : '{pEndPoint}',			
    resource : 0, 
    recContentType : 'text/html', 
    referer : 'http://127.0.0.1:1080/WebTours/home.html', 
    snapshot : 't10.inf', 
    mode : 'HTML'
    }
  );
{% endhighlight %}

`{pEndPoint}` is the run parameter which can be changed to:

    http://api.search.yahoo.com/NewsSearchService/V1/

NOTE: The `mode: HTML` activates a feature of LoadRunner which 
scans the html returned and issue requests for 
links to CSS, JavaScript, images, etc.

(Images specified within CSS are not retrieved this way)

CHALLENGE: Change to `mode: HTTP` for LoadRunner to NOT request links as well.

You can generate only invididual resource requests during recording by setting:

   <img src="/images/LR1250 Recording Recording option 1034x204.png">


### Image by Screen Name

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


### Use generic functions

The function above can instead be called using a generic function
such as:

{% highlight html %}
var rc=0;
rc = wi.web.image( "Search Flights Button", "Search Flights Button" );
if( rc != 0 ){
   lr.outputMessage(">> ERROR Logged-in=" + lr.evalString( "{UserIds_userid}" ));
   // Handle error here.
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

   web.image( in_name, in_alt )
   {
       name : _in_name, 
       alt : _in_alt, 
       snapshot : 't3.inf'
   }

   return rc;
);
{% endhighlight %}

The variable rc (return code) is set at the front of the function  
so the function can return a status.  


### OutputMessage

PROTIP: Do not use generic functions to output messages. 

{% highlight html %}
lr.outputMessage(">> Logged-in=" + lr.evalString( "{UserIds_userid}" ));
{% endhighlight %}

PROTIP: Specify a special set of characters at the front of output messages
so they are easy to identify among potentially many output lines.

NOTE: There are other types of messages.

### Register Find String after download

To scan the stream after receipt to identify a string of text:

{% highlight html %}
web.regFind(
{
   text : 'Find Flight', search : 'Body'
}
);
{% endhighlight %}

CAUTION: An error would be raised immediately if the text is not found.

CHALLENGE: Look at the Help screen for the function to come up with a way to  
fail if the text is found (such as an error message).


### Capture Parameter Extended

To have LoadRunner count the number of times it finds text in the input stream:

{% highlight html %}
web.regSaveParamEx(
{
    foundvar : ????,
    paramName : 'departDate', 
    lb : 'name=\"departDate\" value=\"', 
    rb : '\"', 
    scope : 'Body', 
    requestUrl : '*/reservations.pl*'
}
);
{% endhighlight %}

The code to take action depending on what is in the variable updated:  

???

<hr />

### Generic Start and End Transaction Functions

PROTIP: Replace think-time functions with a generic function:

   wi.StartTrans( pCurrentTrans, rc );

Add a call to end transaction:

   rc = wi.EndTrans( pCurrentTrans, rc );


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



<hr />

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

