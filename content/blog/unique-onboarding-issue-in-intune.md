---
date: 2020-05-09 00:00:00 -0500
draft: false
title: Unique Onboarding Issue in Intune
image: ''
tags:
- Onboarding
- DefenderATP

---
There was a unique case that I had to open with Microsoft regarding onboarding from Intune (autopilot). The configuration profile for Defender ATP was a little bit challenging at first. 

(picture of profile not showing up the onboarding upload) 

So unfortunately, in order of the upload to show up, You need to log into the Defender ATP portal and disconnect from Intune 

(picture of the advance settings and sync is disable)

(then picture of the onboarding profile)

So, apparently my onboarding profile was already expired (might be because of the test/trial tenant from before). Currently, the 'automated'onboarding would onboard the device to "North Europe". Our current ATP tenant is located in the US. So that device never shows up on our portal. 

Once you unsync Defender from Intune, You can upload the onboarding package and this is normally successful and I was able to do it. 

Now the challenging part, we need the sync between Defender and Intune, so this must be fixed. What I found out is that you can create a custom uri for the onboarder. 

(Picture of the onboarding "string") 

After this, is  done, you can deploy the profile and this should still sync up your two components AND be able to onboard devices efficiently. 

Official word from Microsoft Defender Team was, "future fix is needed for this unique circumstances" 

Oh well right?

Thank you, and I hope this helps!