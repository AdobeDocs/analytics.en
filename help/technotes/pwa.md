---
title: PWAs for Analytics
description: Progressive web apps for Adobe Analytics
role: User, Admin
feature: Progressive Web Apps
exl-id: f28e0bfc-0e3e-4f28-9533-6788a36d37fe
---
# PWAs for Adobe Analytics

This page describes how to use Adobe Analytics with Progressive Web Apps (PWAs).

## Introduction

PWAs can provide a native app experience, as well as offline capabilities, for a website. Usually PWAs include a service worker, caching provisions, and a manifest file, all of which can help with faster load times, easier navigation, and responsive behavior.

Adobe Analytics works as seamlessly with PWAs as it does with traditional websites. Although PWAs have a few more requirements to behave progressively in and of themselves, they do not create any barriers or limitations on how Analytics gathers or reports data from them any differently than traditional websites. In fact, because Analytics already includes offline tracking capabilities, PWAs can help you leverage this built-in feature more easily than with traditional websites.

## Get your PWA Analytics data

To collect and analyze your PWA data with [!UICONTROL Analytics], you do not need to  make any configuration changes. [!UICONTROL Analytics] automatically provides all the same functionality and features as it would with a traditional website.

## Add offline tracking to increase PWA effectiveness

You can increase the effectiveness of your PWA by using Adobe Analytics [offline tracking capabilities](/help/implement/vars/config-vars/trackoffline.md) with it. By default, this feature is turned off, but you can add the following property to the AppMeasurement.js file to turn it on: `s.trackOffline=true;`.

For example, in the following AppMeasurement.js file, the property is added to the end of the `CONFIG SECTION`:

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
/* Link Tracking Config */ 
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.trackInlineStats=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx" 
s.linkInternalFilters="javascript:" //optional: add your internal domain here 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
s.trackOffline=true
*** 
```

For more information about configuring the AppMeasurement.js file, see [Configuration variables overview](/help/implement/vars/config-vars/configuration-variables.md) and the individual variable-specific pages in the same subchapter.

For more information on the characteristics of the AppMeasurement.js file, see the [JavaScript implementation overview](/help/implement/js/overview.md).
