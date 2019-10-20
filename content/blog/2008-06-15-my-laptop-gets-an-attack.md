---
title: My Laptop Gets An Attack!
author: sathya
type: post
date: 2008-06-15T08:19:21+00:00
url: /2008/06/15/my-laptop-gets-an-attack/
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/05/19/i-wanna-blow-up-my-school/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2967098" target="_parent" onclick="return BlogGlue.go(event, this, 2949029, 2967098);" title="I Wanna Blow up My School! » My World">I Wanna Blow up My School! » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/03/02/my-new-baby/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2959680" target="_parent" onclick="return BlogGlue.go(event, this, 2949029, 2959680);" title="My new baby » My World">My new baby » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/04/05/appraisals-appraisals/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2950752" target="_parent" onclick="return BlogGlue.go(event, this, 2949029, 2950752);" title="Appraisals, Appraisals » My World">Appraisals, Appraisals » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2949029" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2949029.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325534727"
categories:
  - Computing
tags:
  - antivirus
  - AV
  - exploit
  - Kaspersky
  - trojan
  - virus
  - vulnerability
  - worm

---
A virus attack that is. After more than 8 months of virus-free computing(without using a Anti-Virus too, I might add) my laptop finally bit the bug(so to speak). It happened day-before yesterday, oddly seems to have triggered off after installation of Windows Media Player 11(<a rel="nofollow" href="http://santoshgs.com/" target="_blank">Santosh</a> was praising it, so I thought I’ll check it out). Downloaded it, got it <a href="http://en.wikipedia.org/wiki/Windows_Genuine_Advantage" target="_blank">WGA’d</a>(yes my Windows XP SP2 is Genuine, OEM) and installed. First signs of trouble was when Windows Explorer kept throwing Data Execution Prevention Errors(<a href="http://en.wikipedia.org/wiki/Data_Execution_Prevention" target="_blank">DEP</a>) while browsing through my Music partition. Then WMP11 kept crashing when trying to add my Audio collection(roughly about 7.65 GB).

<!--more-->

[ad]

Further analysis revealed that it kept crashing only when adding Metric’s album Grow Up and Blow Away. Thought it was weird, for WMP to keep crashing for that particular album, so I launched Windows Explorer to navigate to that folder. And lo! No sooner I opened my Music Partition I found random files

  * Seduction secrets
  * MySexMovie
  * MySexPicture
  * WallPaper
  * anna
  * Windows serial number
  * GoogleHack

All these seemed jpeg files, but where actually exe/pif files(yes. I have “Hide extensions for Known File types Disabled”). I saw this and knew instantly that my system had a trojan/worm attack, and immediately disconnected from the Net(further reading on the worm made me realize that the it downloads these files from the net). Since I didn’t have any Anti Virus with me, I installed Kaspersky from the Chip DVD, and started scanning my system, And Bingo! got them all cleaned out. I still had to do some leftover cleanups, which I <span style="text-decoration: line-through;">will post soon</span> [**have posted here**][1].

I’m still wondering how my system got infected though. I’ve disabled AutoRun for Pen drives alone(as I’ve mentioned in <a href="http://sathyabh.at/2008/05/04/ enabledisable-autoplay-for-individual-drives/" target="_blank">this post</a>), and I make sure I open all drives via right-click open rather than blindly double-clicking them.

Besides, the virus description tells me that the method of propagation of virus is

  * Email
  * Local network

Now I’d given up using a local email-client long time ago, and my laptop isn’t on ANY network. My only guess is that this worm was sitting dormant, and the installation and subsequent use of Windows Media Player 11(have never used WMP on my laptop before) triggered off the virus infection, since it makes use of the <a rel="nofollow" href="http://www3.ca.com/securityadvisor/vulninfo/vuln.aspx?id=33721" target="_blank">MS06-001 vulnerability</a>.

Well that’s just my guess anyway. In the end, ended up scanning my entire HDD, no other virus were found. I might go in for a reinstall, though, nothing quite like a Windows reinstall for that perfect cleanup.

[ad]

<div id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:58c64f45-88c3-4d84-935f-18d25e747d77" class="wlWriterSmartContent" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati Tags: <a rel="tag" href="http://technorati.com/tags/sathyabh.at">sathyabh.at</a>,<a rel="tag" href="http://technorati.com/tags/my+world+virus">my world virus</a>,<a rel="tag" href="http://technorati.com/tags/trojan">trojan</a>,<a rel="tag" href="http://technorati.com/tags/worm">worm</a>,<a rel="tag" href="http://technorati.com/tags/antivirus">antivirus</a>,<a rel="tag" href="http://technorati.com/tags/AV">AV</a>,<a rel="tag" href="http://technorati.com/tags/Kaspersky">Kaspersky</a>,<a rel="tag" href="http://technorati.com/tags/exploit">exploit</a>,<a rel="tag" href="http://technorati.com/tags/vulnerability">vulnerability</a>
</div>

 [1]: http://sathyabh.at/2008/06/15/how-to-removing-worm-womble-d-virus-worm/