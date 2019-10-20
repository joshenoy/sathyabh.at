---
title: Fixing Internet Explorer Crash on Launching Oracle Forms Application with jInitiator
author: sathya
type: post
date: 2009-06-26T21:29:20+00:00
url: /2009/06/27/fixing-internet-explorer-crash-on-launching-oracle-forms-application-with-jinitiator/
aktt_notify_twitter:
  - 'no'
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/01/19/my-laptop-chronicles-obtainingor-trying-to-obtain-a-bsnl-evdo-connection-part-1/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947642" target="_parent" onclick="return BlogGlue.go(event, this, 2942135, 2947642);" title="My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World">My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/05/27/dress-up-gmail-with-skins-and-improve-the-functionality/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2965328" target="_parent" onclick="return BlogGlue.go(event, this, 2942135, 2965328);" title="Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World">Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/03/30/how-to-change-the-themes-and-icons-of-sony-ericsson-p1i/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947746" target="_parent" onclick="return BlogGlue.go(event, this, 2942135, 2947746);" title="How-to: Change the themes and icons of Sony Ericsson P1i » My World">How-to: Change the themes and icons of Sony Ericsson P1i » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942135" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942135.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325792094"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
  - Programming
tags:
  - Forms
  - IE
  - Internet Explorer
  - jinitiator
  - oracle

---
I&#8217;ve been facing this really annoying problem for quite some time now. My job revolves around developing apps using [Oracle Forms Builder][1]{#aptureLink_dzpThUVtnA}. Oracle Forms applications, uses Java applets to run inside any browser, on most platforms. Here&#8217;s the kink &#8211; Oracle Forms applications by default uses [Oracle&#8217;s][2]{#aptureLink_5VcUe7aCHj} [jInitiator][3]{#aptureLink_uyXnIMpqB7} which is a JVM made by Oracle and allows a web enabled <a style="text-decoration: none; background-image: none; background-repeat: initial; background-attachment: initial; -webkit-background-clip: initial; -webkit-background-origin: initial; background-color: initial; color: #5a3696; background-position: initial initial;" title="Oracle Forms" href="http://en.wikipedia.org/wiki/Oracle_Forms">Oracle Forms</a> client application to be run inside a web browser.

As much as I hate using Internet Explorer &#8211; I have to depend on it as the my app depends on other components which are designed on run on Internet Explorer only 😐 

Till now I&#8217;ve been using Mozilla Firefox, but now the situation demands that I needed to use Internet Explorer. And when I launched Internet Explorer &#8211; Ka boom! Internet Explorer crashes. Did few things, such as disabling all addons, getting rid of Sun&#8217;s JVM et al, but made no difference.

[ad]

Finally, I came across a solution(or rather a workaround) &#8211; replace the jvm.dll in jinitiator directory with that present in Sun&#8217;s JRE 1.6. If you don&#8217;t want to install the whole bundle &#8211; just [click here][4]{#aptureLink_xEBjE1aaLa}(jvm.dll, 2.2 MB), I&#8217;ve uploaded just the jvm.dll file, rename the original jvm.dll (present in jinitiator/bin/hotspot directory) to, say jvm.dll.old, and replace it with the one given in the above link. Restart the browser, IE shouldn&#8217;t crash anymore.

 [1]: http://en.wikipedia.org/wiki/Oracle%20Forms
 [2]: http://en.wikipedia.org/wiki/Oracle%20Corporation
 [3]: http://en.wikipedia.org/wiki/Jinitiator
 [4]: http://files.getdropbox.com/u/3353/jvm.dll