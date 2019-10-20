---
title: Websense redirect – My First Chrome Extension
author: sathya
type: post
date: 2011-02-04T10:35:11+00:00
url: /2011/02/04/websense-redirect-my-first-chrome-extension/
topsy_short_url:
  - http://u.sbhat.me/ibc1iF
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/01/19/my-laptop-chronicles-obtainingor-trying-to-obtain-a-bsnl-evdo-connection-part-1/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947642" target="_parent" onclick="return BlogGlue.go(event, this, 2942103, 2947642);" title="My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World">My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/04/05/appraisals-appraisals/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2950752" target="_parent" onclick="return BlogGlue.go(event, this, 2942103, 2950752);" title="Appraisals, Appraisals » My World">Appraisals, Appraisals » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/09/21/onsite-opportunity-beckons/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942168" target="_parent" onclick="return BlogGlue.go(event, this, 2942103, 2942168);" title="Onsite opportunity beckons » My World">Onsite opportunity beckons » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942103" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942103.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325785815"
categories:
  - Programming
tags:
  - Chrome
  - Extension
  - extensions
  - Google Chrome
  - Google Chrome Extension
  - javascript
  - webnonsense

---
At my (current) workplace we have a webfiltering mechanism powered by [WebSense][1]. I&#8217;ve [ranted][2] enough number of times on twitter about websense&#8217;s [stupid][3] filtering mechanisms & the [bizarre][4] [classification][5] that it uses to [classify websites][6].  
<!--more-->

  
Recently, I found that fetching the mobile(aka text-only) versions of webpages using instapaper/google web transcoder would result in me being able to read the content &#8211; which was a very nice alternative because majority of the time, I&#8217;d be reading up on posts which are text heavy in nature. It was getting irritating to open to a webpage, encounter a blocked page, open another tab & copy-paste the URL to instapaper to grab the text version. I [asked my peers][7] are [Super User][8]:

> is there a ModRewrite-like extension for chrome ? :-s

[TomWij][9] pointed me towards Privoxy but that was not what I needed. So I decided to build a Chrome Extension. The first version of the extension I built fairly quickly, but required manual intervention by way of clicking on the Extension icon to trigger the redirect &#8211; clearly not an ideal solution. Taking a deeper look at Chrome Extension API docs, I realized that I needed to build a [content script][10].

Building up on this &#8211; I created a simple extension which checks for websense blocking pattern and if so &#8211; redirects it to instapaper which then fetches the text-only version. While this extension is not really the best-thing-since-sliced-bread, it&#8217;s of immense use to me. (And of course, I learnt to build a Chrome Extension, which I always wanted to do).

There are certain bugs, but I can live with those for the moment. If you need a similar thing &#8211; do try out my extension &#8212; it&#8217;s hosted on my servers & can be downloaded from over [here][11]. Let me know if you run into problems.

 [1]: http://www.websense.com/content/home.aspx
 [2]: http://twitoaster.com/country-in/sathyabhat/congrats-reddit-you-have-now-been-promoted-to-the-rank-of-a-social-network-by-webnonsense/
 [3]: twitter.com/SathyaBhat/statuses/28059352136945664
 [4]: http://tumble.sathyabh.at/post/587335342/more-webnonsense-stupidity
 [5]: ttp://friendfeed.com/100rabh/1cec68cc/rt-sathyabhat-all-hail-web-non-sense-says-hacker
 [6]: http://tumble.sathyabh.at/post/49820040/web-non-sense
 [7]: http://chat.stackexchange.com/transcript/118?m=437454#437454
 [8]: http://superuser.com/users/4377/sathya
 [9]: http://superuser.com/users/9666/tomwij
 [10]: http://code.google.com/chrome/extensions/content_scripts.html
 [11]: http://u.sbhat.me/webnonsense