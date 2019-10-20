---
title: Take a screenshot of your desktop and upload to ImageShack imgur easily
author: sathya
type: post
date: 2010-02-25T01:28:04+00:00
url: /2010/02/25/take-a-screenshot-of-your-desktop-and-upload-to-imageshack-easily/
topsy_short_url:
  - http://bit.ly/dndzI4
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/05/27/dress-up-gmail-with-skins-and-improve-the-functionality/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2965328" target="_parent" onclick="return BlogGlue.go(event, this, 2942125, 2965328);" title="Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World">Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/03/30/how-to-change-the-themes-and-icons-of-sony-ericsson-p1i/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947746" target="_parent" onclick="return BlogGlue.go(event, this, 2942125, 2947746);" title="How-to: Change the themes and icons of Sony Ericsson P1i » My World">How-to: Change the themes and icons of Sony Ericsson P1i » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2009/02/24/3-months-and-more-to-come/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942142" target="_parent" onclick="return BlogGlue.go(event, this, 2942125, 2942142);" title="3 Months… And More to Come! » My World">3 Months… And More to Come! » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942125" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942125.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325778409"
categories:
  - Programming
tags:
  - .net
  - 'c#'
  - imageshack
  - imageshack uploader
  - Programming
  - uploader

---
I wanted a simple tool to upload to Imageshack with minimum fuss and absolutely no config settings, couldn&#8217;t find any such so I built one myself.  Just extract all the files to a folder, run the executable, and if you want to upload something to  Imageshack, hit PrintScreen and double click the icon on the system tray, it&#8217;ll automatically upload to <s>ImageShack</s> imgur, and once upload is done, will give you a notification and copy the <s>ImageShack</s> imgur URL to the clipboard.

<!--more-->

  
I&#8217;ve been using this for the past few <span style="text-decoration: line-through;">weeks</span> months now, and seems to work fine atleast on Win 7. Under Linux, the app runs fine using Mono + Winforms without any changes &#8211; although there&#8217;s a slight glitch &#8211; the generated URL doesn&#8217;t see to get copied to the clipboard. Let me know your feedback / rants.

(PS: Don&#8217;t judge my code, its horribly n00bish and nowhere close to being called &#8220;professional&#8221;)

[Download Link:][1]  
Sources available on [GitHub][2]

( Based on [Omkar&#8217;s][3] ScreenUp <del datetime="2010-06-02T01:32:56+00:00">and uses <a href="http://www.codeemporium.com/2009/06/14/dot-net-c-sharp-wrapper-for-the-imageshack-xml-api">Bryce&#8217;s C# Wrapper for ImageShack XML API</a></del>. Also, thanks to Omkar for the [selection screenshot library][4]. )

Screenshot of the software in action:  
![IS Uploader][5] 

Update: Bryce&#8217;s imageshack library stopped working, due to a probable change in API by Imageshack. The tool now uploads the image to imgur. Functionality remains the same 🙂

 [1]: http://j.mp/cFESGw
 [2]: http://github.com/SathyaBhat/imageshackuploader
 [3]: http://intelomkar.wordpress.com
 [4]: http://intelomkar.wordpress.com/2009/12/21/screencapture-library/
 [5]: http://img704.imageshack.us/img704/8379/uploadk.jpg