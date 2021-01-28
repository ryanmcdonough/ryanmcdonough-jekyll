---
id: 38
title: 'Running jQuery &#038; JS from VB.net easily'
date: 2012-06-28T08:24:12+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=38
permalink: /2012/06/running-jquery-js-vb-net-easily/
categories:
  - Code
---
If you need to run some JS or jQuery on an ASP.NET page then the following code will be useful:

<p style="padding-left: 30px;">
  Private Sub runjQueryCode(ByVal jsCodetoRun As String)<br /> Dim requestSM As ScriptManager = ScriptManager.GetCurrent(Me)<br /> If requestSM IsNot Nothing AndAlso requestSM.IsInAsyncPostBack Then<br /> ScriptManager.RegisterClientScriptBlock(Me, GetType(Page), Guid.NewGuid().ToString(), getjQueryCode(jsCodetoRun), True)<br /> Else<br /> ClientScript.RegisterClientScriptBlock(GetType(Page), Guid.NewGuid().ToString(), getjQueryCode(jsCodetoRun), True)<br /> End If<br /> End Sub
</p>

<p style="padding-left: 30px;">
  Private Function getjQueryCode(ByVal jsCodetoRun As String) As String<br /> Dim sb As New StringBuilder()<br /> sb.AppendLine(&#8220;$(document).ready(function() {&#8220;)<br /> sb.AppendLine(jsCodetoRun)<br /> sb.AppendLine(&#8221; });&#8221;)
</p>

<p style="padding-left: 30px;">
              Return sb.ToString()<br /> End Function
</p>

**You can then call the function using: runjQueryCode(jscodetorun)**