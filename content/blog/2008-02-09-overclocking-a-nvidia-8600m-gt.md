---
title: Overclocking a NVIDIA 8600m GT
author: sathya
type: post
date: 2008-02-08T21:39:01+00:00
url: /2008/02/09/overclocking-a-nvidia-8600m-gt/
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/05/07/im-on-foldinghome/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2962787" target="_parent" onclick="return BlogGlue.go(event, this, 2950343, 2962787);" title="I&#39;m on Folding@Home » My World">I&#39;m on Folding@Home » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/04/05/appraisals-appraisals/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2950752" target="_parent" onclick="return BlogGlue.go(event, this, 2950343, 2950752);" title="Appraisals, Appraisals » My World">Appraisals, Appraisals » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/06/12/a-look-at-codemasters-grid/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2954395" target="_parent" onclick="return BlogGlue.go(event, this, 2950343, 2954395);" title="A Look At Codemasters&#39; GRID » My World">A Look At Codemasters&#39; GRID » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2950343" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2950343.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325774161"
categories:
  - Tutorials
tags:
  - ATiTool
  - NVIDIA
  - OC
  - overclock

---
### Requirements

  * Latest nVidia drivers
  * ATiTool 0.26/RivaTuner 2.06
  * A bit of patience

1. Getting the latest drivers.  
Unfortunately, the drivers from nvidia&#8217;s site won&#8217;t work for a laptop, as they don&#8217;t recognize the mobile versions. What you need are drivers from http://www.laptopvideo2go.com Also do note that NOT ALL drivers support OC&#8217;ing. The latest that I tried were 171.16.

Grab the latest drivers from [here][1]. Also, pick up the modified inf files from the same thread. Now extract the downloaded drivers to a folder(the .exe is a self extracting 7z compressed file). Next, goto the folder where the drivers are extracted. Replace the inf file with the modded inf file you have downloaded. DO NOT run the setup.exe file. You will have to update the drivers manually, using the Have Disk Method.  
To do this, goto Control Panel, Double click the System, Click on Hardware Tab and Choose the Device Manager. Expand Display adapters, right click on the 8600m GT and Click on Properties. Click on Driver tab, and Choose update drivers.  
<!--more-->

  
![Update][2] 

Select no when prompted to Check for drivers using Windows Update .

Next, click on Install from a list or specific location.  
![Update from specific location][3]  
Click on Next. In the next dialog, click on Don&#8217;t search radio button and Click next.  
![Manual Install][4]  
In the next dialog, click on Have Disk button, and point to the location where you extracted the inf files,  
click on open and click on Next.  
![Have Disk][5]  
When prompted to restart the system, do so.  
After this, you&#8217;re ready to start overclocking!  
Install ATiTool and run it.  
![ATi Tool][6]  
The last 2 sliders(Core and memory for 3D performance sliders) are what&#8217;s required. Start increasing the Core speed slider, by 5MHz at time, and click on Set Clock button. Once this is done, click on scan artifacts. If the cube is rendered perfectly, then repeat the process.  
![No Artifacts][7]  
At a certain clock, you will start to see artifacts(as seen in the picture).  
![Artifacting][8]  
Even at the slightest hints of artifacts, reduce the speed by about 10MHz, and Click on Scan for artifacts. Once you&#8217;ve reached a sweetspot, Click on scan artifacts again, and let it run for a longer time. Or just play your favorite game, for an hour or so. Any signs of instability, or artifacts, or extremely high temperatures, higher than about 66-68 deg , reduce the speeds immediately! Run repeat the same steps for the memory clocks too. Once you&#8217;ve finalized on the speeds, Click on New, give a suitable name and save the profile. Next time you want to play a game, just load AtiTool, and load the desired profile! Hope this helps!

Performance Results:

Stock speed: 475(core)/400(mem)  
3dMark 06 Results  
Using 163.16 drivers (stock speeds): **3382 3D Marks** 

OC was not possible with this one

171.16 drivers(stock speeds) : **3587 3D Marks** &#8211;> ~200 points increase with just a driver upgrade!

OC&#8217;d speeds: 630/505(any higher than 640 would give artifacts, so to give a comfortable margin, set it to 630): **4396 3D Marks** 😀 \:D/

Nearly a 1000point increase. I think increasing the mem clock I can crack the 4500 mark, but with the current clocks, the peak temp is 66, so I&#8217;m happy \:D/

 [1]: http://www.laptopvideo2go.com/forum/index.php?showforum=73
 [2]: http://img225.imageshack.us/img225/2740/updatexm8.jpg
 [3]: http://img136.imageshack.us/img136/1663/update1bb8.jpg
 [4]: http://img218.imageshack.us/img218/8094/update2nf2.jpg
 [5]: http://img221.imageshack.us/img221/601/update3bz2.jpg
 [6]: http://img221.imageshack.us/img221/8127/atitoolmo3.jpg
 [7]: http://img240.imageshack.us/img240/518/noartifactsrz8.jpg
 [8]: http://img233.imageshack.us/img233/8664/artifactslo6.jpg