---
description: The pageType variable is used only to designate a 404 (Page Not Found) error page.
keywords: Analytics Implementation
seo-description: The pageType variable is used only to designate a 404 (Page Not Found) error page.
seo-title: Setting the PageType variable incorrectly
solution: Analytics
subtopic: Troubleshooting
title: Setting the PageType variable incorrectly
topic: Developer and implementation
uuid: d8f34f76-463e-4708-84e8-0859afa8358c
index: y
internal: n
snippet: y
---

# Setting the PageType variable incorrectly

The pageType variable is used only to designate a 404 (Page Not Found) error page.

 It has only one possible value, which is errorPage. 

```js
pageType="errorPage"
```

On a 404 error page, the *`pageName`* variable should not be populated. The *`pageType`* variable should be set only on a designated 404 error page. Any page containing content should never have a value in the *`pageType`* variable. For pages containing content, you can set the variable as shown below: 

```js
pageType=""
```

It is best to delete the variable completely from pages containing content. This practice is recommended to avoid confusion regarding the purpose of the variable. 
