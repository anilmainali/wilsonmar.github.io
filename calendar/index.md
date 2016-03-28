---
layout: page
title: Please send me an appointment
tags: [calendar, contact, Jekyll]
comments: true
image:
  feature: scr white blue google calendar wilsonmar 1900x500.jpg
  credit:
  creditlink:
---
{% include _toc.html %}

Pick a time from my <a target="_blank" href="https://www.google.com/calendar/embed?src=wilsonmar%40gmail.com
"><strong>public Google calendar</strong>:

NOTE: I usually am up by 4 am Pacific Time (5 am Mountain, 6 am Central, 7 am Eastern).

0. The yellow column is today. Scroll to see the red line which marks the current time.

0. Be aware of the time zone at the lower left corner of the screen.

0. Click on the <u><strong>This Week</strong></u> blue link at the upper right corner.

0. Switch back and forward between your own calendar and this one to identify a mutually open time.

NOTE: In this calendar I keep only the times I cannot move.
I have a separate calendar I use to plan my day.


## Coming Up

On May 1, I'll be in Orlando, Florida for 
<strong><a target="_blank" href="https://stareast.techwell.com/">
StarEast</a></strong>. It's one of a <a target="_blank" href="https://www.techwell.com/software-conferences/star-software-testing-conferences">
series</a>

Come attend my classes:

* <strong><a target="_blank" href="https://stareast.techwell.com/program/preconference-training/mastering-hp-loadrunner-performance-testing-stareast-2016">
Performance Testing 2-days Sunday & Monday</a></strong>.

* <strong><a target="_blank" href="https://stareast.techwell.com/program/preconference-training/mastering-hp-loadrunner-performance-testing-stareast-2016">Git and GitHub half-day Tuesday May 3</a></strong>.
You'll leave with a new free blog website!

* A one-hour introduction to Git and GitHub terms and workflows on Wednesday afternoon.


## Update Jekyll Theme with Calendar
The author pane at the left of this theme was updated to add Calendar under the email link.

0. First, I searched for the Calendar icon in FontAwesome (it's "fa-calendar").

0. Next, had to encode "@" to "%40" in the URL.

0. Finally, this was pasted into the <strong>_author-bio.html</strong> file within the <strong>_includes</strong> folder:

   <pre><code>
   &#123;% if author.email %}<a href="https://www.google.com/calendar/embed?src=<br>
      &#123;&#123; author.email | replace: "@", "%40" }}"<br>
      class="author-social" target="_blank"><br>
      &LT;i class="fa fa-fw fa-calendar">&LT;/i> Calendar</a><br>
   &#123;% endif %}
   </code></pre>


## Load .ics files into Google Calendar
If you clicked on a "Add to your calendar" link and ended up receiving an .ics file in your Downloads folder, here's what to do.

If you have Outlook, just click on the file.

If you use Google Calendar, import the .ics file:

0. If a ZIP file, unzip it and import each .ics file individually.

0. Open <a target="_blank" href="https://calendar.google.com/">Google Calendar</a>.

   Note: You can only import from a computer, not a phone or tablet.

0. Click click the Settings gear button at the top right.

0. Select Settings.

0. Click to open the blue <u>Calendars</u> tab.

0. Scroll down to click the blue <u>Import calendars</u> tab.

0. Click <strong>Choose File</strong> to open a dialog.

0. Select the Downloads folder.

0. Sort by the Date Modified if you don't see the .ics file.

0. Click to select the .ics file, then Open.

0. Choose which calendar to add the imported events to. By default, events will be imported into your primary calendar.

0. Click Import.

0. Click Close the dialog.

0. Click the browser's back button (or press Alt+left arrow) to return to the calendar.

0. Switch to the Finder or File Explorer and <strong>delete the .ics file</strong> (Move to Trash on Macs).

NOTE: This is a modification of https://support.google.com/calendar/answer/37118?hl=en.



## Twitter

<a class="twitter-timeline"  href="https://twitter.com/wilsonmar" data-widget-id="711272963031470080">Tweets by @wilsonmar</a>
<script>!function(d,s,id){var js,fjs=d.getElementsByTagName(s)[0],p=/^http:/.test(d.location)?'http':'https';if(!d.getElementById(id)){js=d.createElement(s);js.id=id;js.src=p+"://platform.twitter.com/widgets.js";fjs.parentNode.insertBefore(js,fjs);}}(document,"script","twitter-wjs");</script>
          