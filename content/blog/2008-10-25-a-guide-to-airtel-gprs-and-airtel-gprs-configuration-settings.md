---
title: A guide to Airtel GPRS And Airtel GPRS Configuration Settings
author: sathya
type: post
date: 2008-10-25T10:03:54+00:00
url: /2008/10/25/a-guide-to-airtel-gprs-and-airtel-gprs-configuration-settings/

arkayne-cache-post:
  - |
    
    
    
    
arkayne-time-post:
  - "1325789070"
categories:
  - Mobiles
tags:
  - Airtel
  - Airtel Live
  - free
  - free GPRS
  - GPRS
  - Live
  - MO
  - Mobile Office
  - Net on Phone
  - NOP

---
I get quite a lot of mails asking about Airtel&#8217;s GPRS services and their settings, so I thought I&#8217;ll post this here.

First things, you should know that Airtel provides 3 types of GPRS services:

  * Airtel Live
  * Airtel NOP (or Net On Phone)
  * Airtel Mobile Office

So what&#8217;s the differences between them ?

<!--more-->

  1. **Airtel Live** &#8211; Airtel Live is the so-called &#8220;free&#8221; GPRS service. Free in the sense that there are no monthly rentals. You get access ONLY to their Airtel Live portal, where you can download some wallpapers, games, ringtones etc. Note that EXCEPT when explicitly mentioned, these downloads ARE NOT free, and will be charged. Majority of the time, Airtel Live will be activated free of cost, and people start exploring and downloading these games and then wonder why their balance has gone low. Now you know why. There have been instances (has happened to my sister) where just opening Airtel Live Portal has resulted in dwindling of balance/credit.
  2. **Airtel Net-on-Phone (or NOP)** &#8211; <del datetime="2011-01-09T04:43:54+00:00">This is my preferred way of GPRS. You have to pay a rental of Rs.5 a day for pre-paid, or RS 99 a month for post paid. There are NO charges for browsing, downloading(provided you download games, ringtones from free sites like getjar) and the speed- its reasonably okay. What makes NOP a killer is that its reasonably priced, and you get access to ALL sites. There&#8217;re couple of downsides though, such as blocking of ports &#8211; essentially this means that only Port 80 is open(so that your web browser can communicate), and most other ports are blocked &#8211; so you cannot make use of your phone&#8217;s Email client, Instant messenger etc. Other bad part is that you cannot use your Phone as a modem on this plan. Also I&#8217;ve been told that for some circles like Maharashtra, Goa, NOP has been discontinued. I hope they don&#8217;t discontinue it in Chennai circle. It&#8217;ll be huge loss for me!</del> (_**Update**_: This plan is now cancelled.)
  3. **Airtel Mobile Office:** The big daddy of GPRS services &#8211; Mobile is same as that of Net on Phone, except that it&#8217;s charged at <del datetime="2011-01-09T04:43:54+00:00">Rs 15/day</del> for pre-paid users. Postpaid users &#8211; <del datetime="2011-01-09T04:43:54+00:00">I think its like Rs 650 a month for 1GB of usage &#8211; there&#8217;s no Unlimited plan(a huge deal breaker for me)</del> (**_update:_** the tariff now is Rs/ 98 per month w/ a datacap of 2GB, anything over is something on the lines of 3op/10KB). UNLIKE the Net-on-Phone plan, all of the ports are open &#8211; so you&#8217;re free to use an application of your choice, and they&#8217;ll work fine. This plan also allows you to use your phone as a modem, for those emergency-need-to-get-online-ASAP situations.

With a little introduction, lets have a look at configuration and settings.

First, this assumes that you&#8217;ve already activated GPRS. If not, call up customer care(dial 121 from your cellphone) and ask them to activate GPRS. It should be activated within 5 minutes, and you should get the settings soon.

However for some phones the settings might not be accepted, you&#8217;ll have to enter them manually.

So in your phone, just search for a settings -> Internet/Data accounts -> Create a new account.

Enter the following details:

**Name:** Just give a name of your choice

**Address or access point or APN:** This is a critical one. The 3 services have different access points.

  * For **Airtel Live**: airtelfun.com
  * For **Airtel Net-On-Phone(NOP):** airtelwap.com
  * For **Airtel Mobile Office:** airtelgprs.com

**Username:** Leave it blank

**Password:** Leave it blank

Next search for Proxy server option, and enter the following details

**Proxy server address/IP:** 100.1.200.99

**Proxy server Port:** 8080

Do note that Proxy details are require **ONLY FOR Airtel Live and Airtel NOP,** Mobile Office doesn&#8217;t require any proxies.

That&#8217;s it! Save the settings, restart your phone(this is a must) and start surfing!
