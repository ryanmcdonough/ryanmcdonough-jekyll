---
id: 132
title: .NET MVC model null on POST
date: 2014-10-29T10:14:11+00:00
author: ryan
layout: post
guid: http://www.ryanmcdonough.co.uk/?p=132
permalink: /2014/10/net-mvc-model-null-post/
categories:
  - Code
tags:
  - .net
  - model
  - mvc
  - 'null'
---
I came across a problem whilst building my latest application, when I was sending a model from a create view the model was showing up null on post.

The code that wasn&#8217;t working:

`public class FileNote<br />
{<br />
public int CaseID { get; set; }<br />
public string Title { get; set; }<br />
public string Note { get; set; }<br />
}`

`[HttpPost]<br />
public ActionResult CreateFileNote(FileNote note)<br />
{<br />
bool fileNoteAdded <span class="p">=</span> FileAccess<span class="p">.Create</span><span class="p">(note);<br />
//etc etc...</span>`

};

Now when the model arrives the object is null, this is because I&#8217;ve named the parameter **note **which is also the same name as one of properties of **FileNote.** The model binder gets confused trying to bind the property of the model rather than the model itself. Changing the code to the below fixes the issue.

`[HttpPost]<br />
public ActionResult CreateFileNote(FileNote <strong>newNote</strong>)<br />
{<br />
bool fileNoteAdded <span class="p">=</span> FileAccess<span class="p">.Create</span><span class="p">(newNote);<br />
//etc etc...</span>`

};