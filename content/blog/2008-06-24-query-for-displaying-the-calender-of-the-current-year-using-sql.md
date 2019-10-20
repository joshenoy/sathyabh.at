---
title: Query For Displaying The Calender of The Current Year using SQL
author: sathya
type: post
date: 2008-06-24T08:45:56+00:00
url: /2008/06/24/query-for-displaying-the-calender-of-the-current-year-using-sql/
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/05/27/dress-up-gmail-with-skins-and-improve-the-functionality/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2965328" target="_parent" onclick="return BlogGlue.go(event, this, 2942191, 2965328);" title="Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World">Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/01/15/the-reason-why-my-room-was-raided/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2956333" target="_parent" onclick="return BlogGlue.go(event, this, 2942191, 2956333);" title="The reason why my room was raided » My World">The reason why my room was raided » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/06/09/animator-vs-animation-the-chosen-one-flash-animation/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2957480" target="_parent" onclick="return BlogGlue.go(event, this, 2942191, 2957480);" title="Animator vs Animation – &quot;The Chosen One&quot; [Flash Animation] » My World">Animator vs Animation – &quot;The Chosen One&quot; [Flash Animation] » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942191" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942191.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325769397"
categories:
  - Computing
tags:
  - calender
  - oracle
  - query
  - SQL

---
Another of things I got via IpMessenger, this query(yes, its a QUERY, not even a full-blown code) returns the calender of the current year. Do note this query will work only in Oracle.

Here&#8217;s the query.  
<!--more-->

> `SELECT LPAD( MONTH, 20-(20-LENGTH(MONTH))/2 ) MONTH,"Sun", "Mon", "Tue",<br />
"Wed", "Thu", "Fri", "Sat"<br />
FROM (SELECT TO_CHAR(dt,'fmMonthfm YYYY') MONTH,TO_CHAR(dt+1,'iw') week,<br />
MAX (DECODE(TO_CHAR(dt,'d'),'1',LPAD(TO_CHAR(dt,'fmdd'),2))) "Sun",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'2',LPAD(TO_CHAR(dt,'fmdd'),2))) "Mon",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'3',LPAD(TO_CHAR(dt,'fmdd'),2))) "Tue",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'4',LPAD(TO_CHAR(dt,'fmdd'),2))) "Wed",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'5',LPAD(TO_CHAR(dt,'fmdd'),2))) "Thu",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'6',LPAD(TO_CHAR(dt,'fmdd'),2))) "Fri",<br />
MAX (DECODE(TO_CHAR(dt,'d'),'7',LPAD(TO_CHAR(dt,'fmdd'),2))) "Sat"<br />
FROM ( SELECT TRUNC(SYSDATE,'y')-1+ROWNUM dt<br />
FROM all_objects<br />
WHERE ROWNUM <= ADD_MONTHS(TRUNC(SYSDATE,'y'),12) - TRUNC(SYSDATE,'y'))<br />
GROUP BY TO_CHAR(dt,'fmMonthfm YYYY'), TO_CHAR( dt+1, 'iw' ))<br />
ORDER BY TO_DATE( MONTH, 'Month YYYY' ), TO_NUMBER(week);`

A screenshot of part of the result returned  
![Calender][1]  
[ad]

 [1]: http://img46.imageshack.us/img46/3879/calenderpngeo2.png