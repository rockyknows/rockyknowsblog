---
date: 2020-05-08 23:21:39 -0500
draft: false
title: 'The Defender Issue #1: Third Party AV and Firewall'
image: "/images/7872_gated(1).png"
tags:
- DefenderATP
- Defender
- DefenderIssue

---

Apparently, People had no idea Defender was even on...

So I've been through hell trying to figure out different issues to our Defender AV is OFF.  
Yes. This happens and there's only a few ways to figure out why and how many..

In the Portal, go to Reporting. You should be able to see the machine compliance. From there, you can filter down to "Defender Anti-Virus - OFF".

There will be a few devices every now and then that are listed under this filter category.  
There are a few ways Defender AV will actually be "OFF".

1. The Windefend service is not running. (Or in some cases, it will fail to start)
2. Third Party Anti-Virus like Norton, McAfee, Panda AV...
3. Group Policy
4. (that's all I can find out right now.. this is a journey!)

![](https://rockyknows.netlify.app/images/dHZQq.png "Service is not running")

This is really a big deal for some but a few of our Virtual Desktops were affected by this. So here's the deal... Our Virtual Desktops are treated very differently so group policy is used to lock down users and in this case, minimal cpu usage. I get it, that's understandable.  
My team never really thought this was causing us headaches but it was.. of course some of these Virtual Desktops are some what slow to get the policy because again, its 'treated' differently.

SOLVED: If you are using SCCM, [please make sure you enable "RUN SCRIPT" ](https://docs.microsoft.com/en-us/configmgr/apps/deploy-use/create-deploy-scripts).

Powershell Code here: (Code will be pasted here soon)

This will set the registry from Disabled(4) to Automatic (2).

**Third Party AV and Firewall**

(tba)

Follow me on twitter [https://twitter.com/atRockyP](https://twitter.com/atRockyP "https://twitter.com/atRockyP")

\+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++