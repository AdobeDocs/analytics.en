---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.registerPreTrackCallback and s.registerPostTrackCallback

These functions take as parameters: the callback (a function), and the parameters to that function. For example:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");

```

The callback is invoked with the `requestUrl` and any parameters passed in when the callback is registered. This occurs either before or after the tracking call, depending on which method is used to register the callback.

The order in which these callbacks are called is not guaranteed. Callbacks registered in the pre function are invoked after the final tracking URL is created. The post callbacks are called upon a successful tracking call (if the tracking call fails, these functions are not called). Any callback registered with `registerPreTrackCallback` do not affect the tracking call. Also, calling any of the tracking methods in any registered callback is not recommended and could cause an infinite loop.
