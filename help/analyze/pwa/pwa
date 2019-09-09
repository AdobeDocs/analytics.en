# PWAs for Analytics

This guide describes how to use Adobe Analytics with Progressive Web Apps (PWAs).

## Introduction

PWAs can provide a native app experience, as well as offline capabilities, for a website. Usually PWAs include a service worker, caching provisions, and a manifest file, all of which can help with faster load times, easier navigation, and responsive behavior. 

Adobe Analytics works just as seamlessly with PWAs as it does with traditional websites. Although PWAs have a few more requirements to behave progressively in and of themselves, they do not create any barriers or limitations on how Analytics gathers or reports data from them any differently than traditional websites. In fact, because Analytics already includes offline tracking capabilities, PWAs can help you leverage this built in feature more easily than with traditional websites.

## Getting your PWA Analytics data

To collect and analyze your PWA data with Analytics, you do not need to  make any configuration changes. Analytics automatically provides all the same functionality and features as it would with a traditional website.

## Add offline tracking to increase PWA effectiveness

You can increase the effectiveness of your PWA by using Analytics [offline tracking capabilities](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/offline-tracking.html) with it. By default, this feature is turned off, but you can add the following property to the AppMeasurement.js file to turn it on: `s.trackOffline=true;`.

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


For more information on editing the AppMeasurement.js file, see [Inserting code into the AppMeasurement.js file](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html).

For examples of configurations in the AppMeasurement.js file, see [Configuring the AppMeasurement.js file](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7).

For more information on the characteristics of the AppMeasurement.js file, see the [Javascript implementation overview](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html). 
