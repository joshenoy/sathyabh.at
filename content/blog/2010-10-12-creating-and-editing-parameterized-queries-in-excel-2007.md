---
title: Creating and Editing Parameterized Queries in Excel 2007
author: sathya
type: post
date: 2010-10-11T22:06:02+00:00
url: /2010/10/12/creating-and-editing-parameterized-queries-in-excel-2007/
topsy_short_url:
  - http://u.sbhat.me/bgWPhQ
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/01/27/the-week-that-was/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947644" target="_parent" onclick="return BlogGlue.go(event, this, 2942111, 2947644);" title="The week that was » My World">The week that was » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/02/17/of-handling-multiple-projects-and-failed-evdo-connections/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2949791" target="_parent" onclick="return BlogGlue.go(event, this, 2942111, 2949791);" title="Of Handling Multiple Projects And Failed EVDO Connections » My World">Of Handling Multiple Projects And Failed EVDO Connections » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2009/09/29/back-in-india/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2942131" target="_parent" onclick="return BlogGlue.go(event, this, 2942111, 2942131);" title="Back In India » My World">Back In India » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2942111" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2942111.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325787726"
categories:
  - Computing
tags:
  - Excel
  - Excel 2007
  - Microsoft Excel
  - parameterized query
  - query
  - SQL

---
I spotted this question on Super User about <a href="http://superuser.com/q/197453/4377" target="_blank">creating parameterized queries in Excel 2007</a> and attempted to answer it &#8211; as I thought it would be pretty easy.

And well &#8211; it was easy &#8211; the part part where you create the query, that is. Now creating _**parameterized**_ queries &#8211; now that&#8217;s something totally different. I searched around a bit for documentation on doing so &#8211; and found that any articles on the same were woefully inadequate. To be specific: There are plenty of articles on how to _change_ the parameters &#8211; just head over to Properties -> Query Definition -> Parameters. Ok, cool. Now hang on, the Parameters button is disabled. How the heck am I supposed to get it enabled ? I had a ball of a time trying to figure out a way to do it &#8211; and in the end, found the answer, and posted it. Figured might as well post it here for my reference&#8230; and for others who are searching for a way to do the same.

<!--more-->

Dunno why MS has made this so complicated, You will have to use Microsoft Query.

Click on Data -> From External Sources -> From Microsoft Query. Choose Data source comes up. Select SQL Server, enter the Authentication details, and select the table

![][1] 

Click on Next, don&#8217;t select any filtering criteria, choose sort by criteria, click on next. Now, click on View/Edit in MS Query instead of selecting Return to Excel

![][2] 

Click on Finish. Now in MS Query, Click on Criteria -> Add Criteria, choose the operator and let the value be `[]`

![][3] 

Click on File -> return data to Excel. Now Excel should prompt you for the parameter, select the relevant cell

![][4] 

To edit the parameters, click on Data -> Properties -> Finger icon -> Definition -> Parameters

![][5] 

* * *You can also use the SQL query editor and type in the query with the joins and put a 

`?` against the field where the parameter has to be fetched.</p> 

![][6]

 [1]: http://i.imgur.com/xgNTl.jpg
 [2]: http://i.imgur.com/UfJ1F.png
 [3]: http://i.imgur.com/TnJoi.png
 [4]: http://i.imgur.com/a2l5C.png
 [5]: http://i.imgur.com/XXhfs.png
 [6]: http://i.imgur.com/NgXxc.png