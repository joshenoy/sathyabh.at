---
title: Batch file to delete files older than x days
author: sathya
type: post
date: 2010-11-10T18:27:21+00:00
url: /2010/11/10/batch-file-to-delete-files-older-than-x-days/
topsy_short_url:
  - http://u.sbhat.me/9qlaoy
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2009/02/24/3-months-and-more-to-come/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942142" target="_parent" onclick="return BlogGlue.go(event, this, 2942108, 2942142);" title="3 Months… And More to Come! » My World">3 Months… And More to Come! » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/03/20/happy-birthday-to-me/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2955817" target="_parent" onclick="return BlogGlue.go(event, this, 2942108, 2955817);" title="Happy Birthday To Me » My World">Happy Birthday To Me » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2011/02/04/websense-redirect-my-first-chrome-extension/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942103" target="_parent" onclick="return BlogGlue.go(event, this, 2942108, 2942103);" title="Websense redirect – My First Chrome Extension » My World">Websense redirect – My First Chrome Extension » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942108" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942108.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325789912"
categories:
  - Computing
tags:
  - backup
  - batch-file
  - command-line
  - commands

---
At work, I have bunch of batch files which take an export from Oracle database, compress them and move them to their respective folders. In addition to this, the scripts also copy the Oracle forms executibles (&#8220;fmx&#8221;), reports (&#8220;rdf&#8221;) and other miscellaneous files to the backup locations and these are further compressed. The compressed files are then transferred over to the [SAN][1]{#aptureLink_VeJbB6l0ht}.

<!--more-->

Now the problem was that these backup files would still remain on the hard drive, littering the folders and resulting in waste of space &#8211; I was looking for an alternative to get rid of these files via a scripted approach. The catch is that this is a Windows server and I&#8217;m restricted to the CLI that Windows provides &#8211; and no PowerShell either. So while researching for ways to select files older than x days, I came across forfiles command on [Stack Overflow][2]{#aptureLink_DBBcWqvGFh} (God bless thee).

<pre class="brush:bash">forfiles: Select a file (or set of files) and execute a command on each file.</pre>

Perfect. Exactly what I needed. After reading the help file and experimenting with it, I rolled out a script which will delete any file older than 30 days.

<pre class="brush:bash">@echo off
@Echo Deleting files older than 30 days...

forfiles /p g:\backup /d -30 /c "cmd /c del @file"</pre>

So this will basically search for any file(s) older than 30 days ( based on the Last Modification Date attribute) in the path g:\backup and will execute del @file where del == delete, @file is the variable which holds the filename.

You can further filter out the files by using /m switch. I&#8217;d recommend you have a look at the description [over here][3]{#aptureLink_H8f0VYDmJa}.

 [1]: http://en.wikipedia.org/wiki/Storage%20area%20network
 [2]: http://stackoverflow.com/q/51054/92837
 [3]: http://ss64.com/nt/forfiles.html