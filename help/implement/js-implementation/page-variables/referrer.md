---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# referrer

The  variable can be used to restore lost referrer information.


<!-- 

referrer.xml

 -->

Server-side and JavaScript redirects are often used to route visitors to proper locations. However, when a browser is redirected, the original referring URL is lost.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  255 bytes  | R  | Traffic > Finding Methods Conversion > Finding Methods  | document.referrer  |

Many companies use redirects in many places throughout their websites. For example, a visitor may be sent through a redirect from a search engine paid search result. When a browser is redirected, the referrer is often lost. The *`referrer`* variable may be used to restore the original *`referrer`* value on the first page after a redirect. The *`referrer`* may be populated server-side, or via JavaScript from the query string.

For Analytics to record a referrer, it must be "well formed," meaning that it must follow the standard URL format, with a protocol and appropriate location.

**Syntax and Possible Values** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Only URL-compatible values should be in the *`referrer`*. Make sure the string is URL encoded (no spaces).

**Examples** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 

```

**Configuration Settings** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

None

**Pitfalls, Questions, and Tips** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.
