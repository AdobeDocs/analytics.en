---
description: The abort flag can be set inside doPlugins to cause the current track call to not be sent.
keywords: Analytics Implementation
seo-description: The abort flag can be set inside doPlugins to cause the current track call to not be sent.
seo-title: s.abort flag
solution: Analytics
title: s.abort flag
topic: Developer and implementation
uuid: 7571b2a1-5326-4764-99cf-66760cc0f26b
index: y
internal: n
snippet: y
---

# s.abort flag

The abort flag can be set inside doPlugins to cause the current track call to not be sent.

The abort flag is reset with every tracking call, so if a subsequent tracking call also needs to be aborted the flag will need to be set again inside doPlugins.

```js
s.doPlugins = function(s) { 
     s.campaign = s.getQueryParam("cid"); 
     if ((!s.campaign) && (!s.events)) { 
          s.abort = true; 
     } 
};
```

This lets you centralize the logic you use to identify activity that you do not want to track, such as some custom links or external links in display ads. 
