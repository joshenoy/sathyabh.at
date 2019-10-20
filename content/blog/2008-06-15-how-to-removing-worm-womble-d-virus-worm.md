---
title: '[How To] Removing Worm/Womble.D – Virus/Worm'
author: sathya
type: post
date: 2008-06-15T09:55:04+00:00
url: /2008/06/15/how-to-removing-worm-womble-d-virus-worm/
arkayne-cache-post:
  - |
    
    
    <script type="text/javascript" defer="defer"> BlogGlue = window.BlogGlue || window.Arkayne || {}; BlogGlue.baseurl = 'http://www.blogglue.com'; BlogGlue.go = function(e, a, cid, gid) { var id = a.getAttribute('id'); var orig = a.getAttribute('href'); var target = a.getAttribute('target'); var redir = [BlogGlue.baseurl, 'link', cid, gid, ''].join('/'); redir += '?ts=' + Math.random(); redir += '&amp;url=' + escape(a.href); a.setAttribute('href', redir); setTimeout('BlogGlue.restore("' + id + '", "' + orig + '")', 0); return true; }; BlogGlue.restore = function(id, orig) { var a = document.getElementById(id); if (a) a.setAttribute('href', orig); }; </script> <div class="blogglue_plugin" style="display:block;margin:5px 0px 20px 0px;"> <h3 class="blogglue-header blogglue-inner"> More From sathyabhat </h3> <ul class="blogglue-links blogglue-inner"> <li id="blogglue-inner-1"><a href="http://sathyabh.at/2008/01/19/my-laptop-chronicles-obtainingor-trying-to-obtain-a-bsnl-evdo-connection-part-1/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947642" target="_parent" onclick="return BlogGlue.go(event, this, 2966544, 2947642);" title="My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World">My Laptop Chronicles: Obtaining(or trying to obtain) a BSNL EVDO connection Part 1 » My World</a></li> <li id="blogglue-inner-2"><a href="http://sathyabh.at/2008/05/27/dress-up-gmail-with-skins-and-improve-the-functionality/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2965328" target="_parent" onclick="return BlogGlue.go(event, this, 2966544, 2965328);" title="Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World">Dress up GMail with Skins – And Improve The Functionality using Better GMail » My World</a></li> <li id="blogglue-inner-3"><a href="http://sathyabh.at/2008/03/30/how-to-change-the-themes-and-icons-of-sony-ericsson-p1i/?utm_source=BlogGlue_network&amp;utm_medium=BlogGlue_Plugin" id="blogglue-2947746" target="_parent" onclick="return BlogGlue.go(event, this, 2966544, 2947746);" title="How-to: Change the themes and icons of Sony Ericsson P1i » My World">How-to: Change the themes and icons of Sony Ericsson P1i » My World</a></li> </ul> <div class="blogglue-footer" style="margin:10px 0px;display:block !important"> <a href="http://www.blogglue.com/12928-ab7e24be6f12e678fc1a468df18f3f3f/?utm_source=BlogGlue%20Plugin&amp;utm_medium=Recommend&amp;utm_campaign=Plugin&amp;coupon=SATHYABHAT&amp;blogglue_page=2966544" target="_blank" style="text-decoration:none !important;"> <img src="http://www.gravatar.com/avatar.php?default=%2F%2Fs3.amazonaws.com%2Farkayne-media%2Fimg%2Fprofile%2Fdefault_sm.png&amp;size=24&amp;gravatar_id=1375f202e61682cc4963295f4b0430dc" width="24" height="24" border="0" alt="Blog Margeting Related Posts Plugin For sathyabhat" style="display:inline;margin: 0 5px 0 10px; border:1px solid #AAA; width: 24px !important; height: 24px; !important;"/><span style="position:relative;top:-8px;font-family:'Trebuchet MS'; font-size: 0.8em;">Ask <strong>sathyabhat</strong> To Recommend Your Posts</span> </a> <img class="blogglue-hit" style="border:none;left:-9999px;position:absolute;" src="http://www.blogglue.com/widget/hit/2966544.GIF" border="0" alt="Blog Marketing Related Posts Plugin Counter" /> </div> </div>
    
arkayne-time-post:
  - "1325765003"
categories:
  - Computing
tags:
  - antivirus
  - AV
  - AVG
  - cleanup
  - Kaspersky
  - NOD32
  - tips
  - Tutorials
  - virus
  - womble
  - Womble.d
  - worm

---
</p> 

Well as mentioned <a href="http://sathyabh.at/2008/06/15/my-laptop-gets-an-attack/" target="_blank">here</a> my system was infected by this worm, so I thought I’d do a short post on how to fix this, as most Anti Virus Programs don’t get rid of this cleanly.

First thing, if you’re on the internet, GO OFFLINE! Disconnect, switch off the modem/router, pull the LAN/USB cable, just go offline. This is critical. Why you may ask?

<!--more-->

[ad]

First, **Womble** is described as 

> Win32/Womble.D is a mass-mailing worm that may be distributed both as an executable or as a malformed Windows Media file exploiting the MS06-001 vulnerability. It may also replicate via network shares. It can be used to periodically download and execute arbitrary files on an affected machine.

And that’s the reason why you have to go offline, since even though the anti-virus might be disinfecting your system, there’s every chance that the worm might keep on downloading and infecting, leading to a never ending process.

Luckily the worm isn’t destructive. Here’s a description of what the worm does:

> It creates the following directories:  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\dvd_info  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\free  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\h_core  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\l_this  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\lunch  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\my_staff  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\new_mp3  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\new_video  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\photo  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\sh_docs  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\take_it  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\video  
> &#160;&#160; • %home%\Local Settings\Application Data\Microsoft\WinTools\xxx 
> 
> It drops copies of itself using a filename from lists, the following names, to all of the above directories  
> &#160;&#160; • bush  
> &#160;&#160; • Me  
> &#160;&#160; • My passwords  
> &#160;&#160; • MyWife  
> &#160;&#160; • Seduction secrets  
> &#160;&#160; • MySexMovie  
> &#160;&#160; • MySexPicture  
> &#160;&#160; • WallPaper  
> &#160;&#160; • anna  
> &#160;&#160; • Windows serial number  
> &#160;&#160; • GoogleHack  
> &#160;&#160; • OurNewCar  
> &#160;&#160; • OurNewHouse 
> 
> &#160;&#160; • .doc  
> &#160;&#160; • .jpg  
> &#160;&#160; • .txt 
> 
> &#160;&#160; • .exe  
> &#160;&#160; • .pif
> 
> It tries to download some files: 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats. 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats. 
> 
> – The location is the following:  
> &#160;&#160; • support.365soft.info/current/\***\***\****  
> This file may contain further download locations and might serve as source for new threats.

Now I hope you have a decent anti-virus software installed. If not, get one! Recommendations include Kaspersky, NOD32 for paid and AVG Free 8 for free anti-virus. Install these, during scanning when prompted with the action, click on Delete.

If you don’t have an AV/can’t install one, then you’ll have to manually remove it for this, open the registry editor, by Clicking on Start, Run and typing regedit and pressing enter.

Navigate to HKEY\_LOCAL\_MACHINE (abbreviated to HKLM) and then delete the following entry

> – [HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run]  
> &#160;&#160; • windows_startup=%SYSDIR%\%random words%.exe

Next, delete the following entries

> – [HKLM\SOFTWARE\WinUpdate]  
> &#160;&#160; • "Version"=dword:00000004 
> 
> – [HKLM\SOFTWARE\WinUpload]  
> &#160;&#160; • "bot1.exe"=dword:00000002  
> &#160;&#160; • "bot2.exe"=dword:00000002  
> &#160;&#160; • "l.exe"=dword:00000002  
> &#160;&#160; • "t169.exe"=dword:00000002 
> 
> – [HKCU\Software\Microsoft\WAB\WAB4]  
> &#160;&#160; • "FirstRun"=dword:00000001 
> 
> – [HKCU\Software\Microsoft\Windows\CurrentVersion]  
> &#160;&#160; • "wmf.1.1"=dword:01c6db12  
> &#160;&#160; • "wmf.1.2"=dword:e8fc9740

where HKCU is an abbreviation for HKEY\_CURRENT\_USER

Then head over to [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon]  
You will see something like 

> [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon] 
> 
>   * "Shell"="Explorer.exe%empty spaces% %SYSDIR%\%random words%.exe"
>   * &#160; "Userinit"="%SYSDIR%\userinit.exe%empty spaces% ,%SYSDIR%\%random words%.exe"

Change these to 

> [HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon] 
> 
>   * "Shell"="Explorer.exe"
>   * "Userinit"="%SYSDIR%\userinit.exe”</p> 

Now reboot your machine. Next, if you’ve Disabled Show Hidden Files, you should enable it by going to My Computer, Tools –> Folder Options, Click on View –> Show Hidden Files.

Next, goto %home%\Local Settings\Application Data\Microsoft\&#160; where %home% is the current user folder, ie, if Windows is installed in C, and the user is user1 then %home% refers to 

C:\Documents And Settings\user1\

Delete the WinTools folder. After this your system should be free from the worm

[ad]</p> 

<div class="wlWriterSmartContent" id="scid:0767317B-992E-4b12-91E0-4F059A8CECA8:82947d79-0f6e-4875-b8be-314c29dd3633" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">
  Technorati Tags: <a href="http://technorati.com/tags/sathyabh.at" rel="tag">sathyabh.at</a>,<a href="http://technorati.com/tags/myworld" rel="tag">myworld</a>,<a href="http://technorati.com/tags/sathya" rel="tag">sathya</a>,<a href="http://technorati.com/tags/virus" rel="tag">virus</a>,<a href="http://technorati.com/tags/worm" rel="tag">worm</a>,<a href="http://technorati.com/tags/AV" rel="tag">AV</a>,<a href="http://technorati.com/tags/antivirus" rel="tag">antivirus</a>,<a href="http://technorati.com/tags/womble" rel="tag">womble</a>,<a href="http://technorati.com/tags/Womble.d" rel="tag">Womble.d</a>,<a href="http://technorati.com/tags/cleanup" rel="tag">cleanup</a>,<a href="http://technorati.com/tags/tips" rel="tag">tips</a>,<a href="http://technorati.com/tags/tutorials" rel="tag">tutorials</a>,<a href="http://technorati.com/tags/AVG" rel="tag">AVG</a>,<a href="http://technorati.com/tags/NOD32" rel="tag">NOD32</a>,<a href="http://technorati.com/tags/Kaspersky" rel="tag">Kaspersky</a>
</div>