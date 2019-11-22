---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# visitorID

Visitors can be identified by the  variable or by IP address/User Agent.


<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

If you explicitly set a custom ID, it will always be used before the other ID methods.

This is the order of use: s.visitorID > s_vi > s_fid > IP/UA.

|  ** Max Size** | ** Debugger Parameter** | ** Reports Populated** | ** Default Value** |
|---|---|---|---|
|  100 bytes  | vid  | n/a  | ""  |

**Syntax and Possible Values** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] The *`visitorID`* variable should not contain a hyphen.

**Examples** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Configuration Settings** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

None 
