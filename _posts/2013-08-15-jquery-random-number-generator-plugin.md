---
id: 86
title: jQuery Pseudo Random Number Generator Plugin
date: 2013-08-15T10:10:27+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=86
permalink: /2013/08/jquery-random-number-generator-plugin/
categories:
  - Code
  - Open Source
tags:
  - high entropy
  - js
  - random number generator
---
Yesterday I released a [jQuery plugin to generate true random numbers](https://github.com/ryanmcdonough/jQuery.uheprnGen) based on the brilliant work done by [Steve Gibson](https://www.grc.com/otg/uheprng.htm) to create an Ultra-High Entropy Pseudo-Random Number Generator.

This takes the work Steve has done, and automates some of the steps used on the demo page such as generating the entropy and setting the range & count for the loops &#8211; though you can change those.

## Example code

<pre>var options = { range: 10001, count: 10001 };</pre>

<pre>var x = $(this).uheprngGen(options);</pre>

You can download the [plugin here from Github](https://github.com/ryanmcdonough/jQuery.uheprnGen).

This plugin was featured on the amazing [DailyJS](http://dailyjs.com/2013/08/20/jquery-roundup/) site.