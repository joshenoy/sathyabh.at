---
title: Making Oracle Forms Use JRE instead of Jinitiator
author: sathya
type: post
date: 2010-11-30T20:50:47+00:00
url: /2010/12/01/making-oracle-forms-use-jre-instead-of-jinitiator/
topsy_short_url:
  - http://u.sbhat.me/g7WwQK
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/05/24/think-twice-before-you-use-a-cheap-psu/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2954665" target="_parent" onclick="return BlogGlue.go(event, this, 2942107, 2954665);" title="Think Twice Before you Use a Cheap PSU! » My World">Think Twice Before you Use a Cheap PSU! » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942107" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942107.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325783414"
categories:
  - 'Oracle &amp; PL/SQL Stuff'
tags:
  - Application Server
  - Forms
  - oracle
  - Oracle Forms
  - PL/SQL
  - work

---
By default, Oracle Forms Application Server serves Oracle Forms applications using the built-in [Jinitiator JVM][1]. While JVM works _swell_ with cutting edge browsers<sup><a href="#footnote_0_424" id="identifier_0_424" class="footnote-link footnote-identifier-link" title="IE6">1</a></sup> it pretty much crashes most of the other browsers<sup><a href="#footnote_1_424" id="identifier_1_424" class="footnote-link footnote-identifier-link" title="Firefox, IE7+">2</a></sup> and doesn&#8217;t work at all in Chrome. There <a href="http://sathyabh.at/2009/06/27/fixing-internet-explorer-crash-on-launching-oracle-forms-application-with-jinitiator/" target="_blank">are workarounds</a> but the workarounds do not play well while working with multiple tabs.

<!--more-->

Here&#8217;s a simple way to make the Application Server serve Oracle Forms Applications using JRE rather than the Jinitiator. Please remember to take a backup of your existing files!

Locate your formsweb.cfg file. It should be in $oracle_home/forms/server directory. Add the below lines to the section corresponding to your config= setting.

<pre class="brush:bash">baseHTMLjinitiator=basejpi.htm
jpi_download_page=http://www.oracle.com/technetwork/java/javase/downloads/index-jdk5-jsp-142662.html
jpi_classid=clsid:8AD9C840-044E-11D1-B3E9-00805F499D93
jpi_codebase=https://java.sun.com/update/1.5.0/jinstall-1_5-windows-i586.cab
jpi_mimetype=application/x-java-applet;version=1.4.2</pre>

Here&#8217;s a brief explanation of each of these terms:

  * jpi_classid – The ClassID of the Sun JVM to use (Internet Explorer specific). Should be set to clsid:8AD9C840-044E-11D1-B3E9-00805F499D93 for dynamic versioning or to clsid:CAFEEFAC-<major version>-<minor version>-<patch version>-ABCDEFFEDCBA for static versioning
  * jpi_codebase – Download location of the CAB file for the Sun JVM (IE specific)
  * jpi\_mimetype – JPI\_MIMETYPE is a mime-type in a format like “application/x-java-applet;<version\_type>=<implementation\_version>”. For static versioning, <version_type> should be set to “jpi-version”. For dynamic versioning, this should be set to “version”.
  * jpi\_download\_page – This is the URL where Netscape/Firefox users can download the JRE.

Refer [here][2] for a detailed explanation of each of these terms. That&#8217;s about it. Reloading the application should result in the JRE kicking in, rather than Jinitiator. Also ensure any jar files that you have are digitally signed, else you will run into an warning about blocking unsigned jar files which might lead to a showstopper bug.

<ol class="footnotes">
  <li id="footnote_0_424" class="footnote">
    IE6 [<a href="#identifier_0_424" class="footnote-link footnote-back-link">&#8617;</a>]
  </li>
  <li id="footnote_1_424" class="footnote">
    Firefox, IE7+ [<a href="#identifier_1_424" class="footnote-link footnote-back-link">&#8617;</a>]
  </li>
</ol>

 [1]: http://en.wikipedia.org/wiki/Jinitiator
 [2]: http://www.oratransplant.nl/2005/05/24/settings-for-dynamic-versioning-with-sun-jpi-and-oracle-forms/