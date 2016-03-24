---
layout: page
title: Budget spreadsheet
modified: 2016-03-01
excerpt: "Your future, in a box."
tags: [budget, spreadsheet, files, jekyll]
image:
  feature: pic white blue spreasheet 1900x500.jpg
  credit: blog.marketo.com
  creditlink: http://blog.marketo.com/2013/06/the-problems-with-using-spreadsheets-to-manage-your-marketing-budget.html
comments: true
---

{% include _toc.html %}

This is part of my Evangelist series:

{% include evangelist_links.html %}

## The spreadsheet

![Click here to download spreadsheet: Dev_evangelism_budget_v02_wm_2016.03.22.xlsx]({{ site.url }}/assets/Dev_evangelism_budget_v02_wm_2016.03.22.xlsx)

BTW, the file was created using Microsoft Office 2011 for Mac.

<!-- WARNING: Word locks the file when it open a file, which makes Jekyll think it doesn't exist.
-->

## The columns

* "#" contains counts of the deliverable.

* Deliverables short description

* Urgency: Number 1 is highest. You may want to use A,B,C,D instead here.

  This column is not used in any calculation.
 
* Effort: Number for estimating, taken from Agile practitioners.

  This number may mean different things to different people.

  The coloring was set by highlighting the column and clicking Word's **Conditional Formatting** icon
  on the Home ribbon or menu Format.

* %: auto-calculated by an Excel formula.

  CAUTION: Typing in this column destroys the calculation.

* Days: The number of man-days. The number in each row is a fraction of the 
  total under the same column within the **Totals** tab.
  A separate tab is used so the Assets sheet can be sorted easier.

  Calculations are based on the percentage of Effort.
  
  CAUTION: Typing in this column destroys the calculation.

* Yield: is for comment about the outcome (FTW)

* Note:

## Usage

This spreadsheet helps you see when you're over-extended with commitments.

Review the man-days to see if it's reasonable, 

The number of days at the bottom should be **work-days** (about 20 a month),
less holidays, vacations, and 
a margin for various more urgent items that 
come up to eat up time along the way.

> It's better to under-commit and over-deliver than<br />over-commit and under-deliver.

You can sort this spreadsheet by various columns.
