---
description: Segmenting paths by user type is a common request for trying to understand how specific user types path on your site.
keywords: Analytics Implementation
seo-description: Segmenting paths by user type is a common request for trying to understand how specific user types path on your site.
seo-title: Segment paths by user type
solution: Analytics
title: Segment paths by user type
topic: Developer and implementation
uuid: 5c298f39-381d-453b-a608-109e3276b361
---

# Segment paths by user type

Segmenting paths by user type is a common request for trying to understand how specific user types path on your site.

You can concatenate the user type and page name into a [!UICONTROL sprop] and enable pathing on the [!UICONTROL sprop].

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. You need to distinguish between these two user types on each page and put these values into your designated [!UICONTROL sprop]. When you populate the prop, it should display as shown below:

```js
 s.prop1=”Registered : “ + s.pageName;
```

If the user is a registered user and visited the home page, the value in the prop displays as follows:

```js
 “Registered : Home Page”
```

If they click to another page named "Page 2", the value on that page displays as follows:

```js
 “Registered : Page 2”
```

With [!UICONTROL Pathing] turned on, you see those two values in succession. If you want to know how registered users move from the home page, find the value "Registered : Home Page" in one of the path reports and see the next pages they visited. In this case, they next went to "Page 2." 
