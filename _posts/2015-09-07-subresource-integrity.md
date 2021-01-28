---
id: 160
title: Subresource integrity
date: 2015-09-07T09:26:07+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=160
permalink: /2015/09/subresource-integrity/
categories:
  - Code
  - Open Source
  - Security
---
[A new feature in Google Chrome 45](https://www.chromestatus.com/feature/6183089948590080) is the ability to add meta data inline to <script> and <link rel=&#8221;stylesheet&#8221;> elements which will allow the browser to determine if the resource which has been downloaded is the same as the author intended.

This is done by adding integrity  metadata to the element inline such as:

> <link rel=&#8221;stylesheet&#8221; href=&#8221;this\_is\_verified.css&#8221; integrity=&#8221;sha256-qvuZLpjL9TNV6yI1kNdGCPnSTrWM6Y0ILEzzyvA9hGY=&#8221;>

You would generate the base64 encoded version of the SHA256 hash with the following command:

> cat this\_is\_verified.css| openssl dgst -sha256 -binary | openssl enc -base64 -A

If the hash doesn&#8217;t match the file and the integrity is compromised the browser will not load the resource.

This is currently in development for Firefox as well, though no news on Edge or Safari for implementation.