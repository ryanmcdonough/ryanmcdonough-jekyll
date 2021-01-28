---
id: 9
title: ASP.NET Session Timeout
date: 2012-03-15T16:43:14+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=9
permalink: /2012/03/asp-net-session-issues/
categories:
  - Code
tags:
  - asp.net
  - inproc
  - session timeout
  - stateserver
---
During a redevelopment of my employers website we had massive issues with session timeout&#8217;s during use of the website during development, even a simple change to a page on the site was causing the application to recompile and then lose the session data.

This was due to the use of InProc (In Process Mode) Mode for the session, to fix this we moved to StateServer using the following setting in the web.config file:

<address>
  <sessionState mode=&#8221;StateServer&#8221; stateConnectionString=&#8221;tcpip=127.0.0.1:42424&#8243; cookieless=&#8221;UseCookies&#8221; timeout=&#8221;60&#8243; regenerateExpiredSessionId=&#8221;true&#8221;/>
</address>

<address>
   
</address>

This now means that even if the application recompiles the session data will remain and will only be lost of the application is restarted or IIS is restarted. Hope this helps anyone searching about session timeouts in asp.net