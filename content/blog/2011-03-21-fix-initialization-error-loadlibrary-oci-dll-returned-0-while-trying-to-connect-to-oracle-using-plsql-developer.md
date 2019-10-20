---
title: 'Fix Initialization Error: LoadLibrary oci.dll returned 0 while trying to connect to Oracle using PL/SQL Developer'
author: sathya
type: post
date: 2011-03-21T08:38:24+00:00
url: /2011/03/21/fix-initialization-error-loadlibrary-oci-dll-returned-0-while-trying-to-connect-to-oracle-using-plsql-developer/
topsy_short_url:
  - http://u.sbhat.me/fP78nY
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2011/02/21/my-nexus-s-homescreens/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942102" target="_parent" onclick="return BlogGlue.go(event, this, 2942101, 2942102);" title="My Nexus S homescreens » My World">My Nexus S homescreens » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/03/20/happy-birthday-to-me/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2955817" target="_parent" onclick="return BlogGlue.go(event, this, 2942101, 2955817);" title="Happy Birthday To Me » My World">Happy Birthday To Me » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942101" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942101.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325789975"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
tags:
  - database
  - instant client
  - oracle
  - PL/SQL
  - PL/SQL Developer

---
Quick post: I was trying to connect to a 64-bit Oracle database using PL/SQL Developer. Despite ORACLE_HOME being set the right values and oci.dll available, PL/SQL Developer could not connect to the database.

<!--more-->

Further probing indicated that the Oracle installation was a 64-bit one, and PL/SQL Developer is incapable of loading 64-bit version of oci.dll file. To fix this, download the 32-bit version of [Oracle Instant Client][1], extract it to a directory such as \instant_client.

Next, configure PL/SQL Developer to use this version by clicking on Tool menus -> Preferences. Under Oracle Home, point to the location where you had extracted Instant client (\instant\_client, in this case)  and under location of OCI Library, point to the oci.dll file present in location where you had extracted Instant client ( \instant\_client\oci.dll). Restart PL/SQL Developer and you should be able to connect now.

 [1]: http://www.oracle.com/technetwork/database/features/instant-client/index-097480.html