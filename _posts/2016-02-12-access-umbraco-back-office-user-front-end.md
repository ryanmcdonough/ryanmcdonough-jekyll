---
id: 173
title: Access Umbraco back office user from the front end
date: 2016-02-12T14:51:16+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=173
permalink: /2016/02/access-umbraco-back-office-user-front-end/
categories:
  - Code
  - Open Source
tags:
  - umbraco
---
If you need to access the current user logged into the Umbraco Backoffice from the Front End (to show a link to administrator area for example) you may have tried:

<pre>umbraco.BusinessLogic.User.GetCurrent()
UmbracoContext.UmbracoUser
UmbracoContext.Security.CurrentUser
umbraco.helper.GetCurrentUmbracoUser()</pre>

None of which seem to work, then you should user the following code:

<pre>@using Umbraco.Core.Security;
var userTicket = new System.Web.HttpContextWrapper(System.Web.HttpContext.Current).GetUmbracoAuthTicket();
if (userTicket != null) {     
 var currentUser = ApplicationContext.Services.UserService.GetByUsername(userTicket.Name);
}</pre>

As Andrew Wilson mentions in the comments, remember to include Umbraco.Core.Security &#8211; though if you forget hopefully Visual Studio will tell you to add it.

**Version 8 Note**

As Corey mentions in the comments, remember to include:

@using Umbraco.Web.Security;

For Umbraco 8 onwards.