---
id: 68
title: Clear Client Browser Cache with IIS
date: 2013-06-14T10:17:08+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=68
permalink: /2013/06/clear-client-browser-cache-with-iis/
categories:
  - Code
tags:
  - cache
  - clear cache
  - iis6
  - iis7
  - web browser cache
---
So you&#8217;ve updated your site and now you realise that some clients can&#8217;t see the changes of images/css because they all retain the same names as the old version?

Well in IIS you can change the Content Expiry Header to force the client to get the latest versions of the files.

For IIS 7 follow the step from [Microsoft](http://technet.microsoft.com/en-us/library/cc770661(v=ws.10).aspx).

  1. In **Features View in IIS**, double-click **HTTP Response Headers**.
  2. On the **HTTP Response Headers** page, in the **Actions** pane, click **Set Common Headers**.
  3. In the **Set Common HTTP Response Headers** dialog box, select the **Expire Web content **check box and select one of the following options: 
      * Select **Immediately** if you want content to expire immediately after it is sent in a response.
      * Select **After** if you want the content to expire periodically. Then, in the corresponding boxes, type an integer and select a time interval at which content expires. For example, type **1** and select **Days** if you want the content to expire daily.
      * Select **On (in Coordinated Universal Time (UTC))** if you want the content to expire on a specific day and at a specific time. Then, in the corresponding boxes, select a date and time at which the content expires.

For IIS 6:

  1. <span style="line-height: 14px;"> In IIS Manager, double-click the local computer; right-click the Web Sites folder, an individual Web site folder, a virtual directory, or a file; and then click <strong>Properties</strong>.<br /> </span>
  2. Click the **HTTP Headers** tab.
  3. Select the **Enable content expiration** check box.
  4. Click Expire immediately, Expire after, or Expire on, and type the appropriate expiration information in the corresponding boxes.

### 

### Clearing the cache with Query String

If you have access to the source code mall modern browsers will treat resources such as a CSS, Javascript as new versions if you append a query string to them which is unique.

E.g

<pre>http://www.ryanmcdonough.co.uk/site.css?v=1.1</pre>

The actual content of the query string doesn&#8217;t matter as long as it&#8217;s unique, however most developers will tend to use v for version and then just set it to be the build number.