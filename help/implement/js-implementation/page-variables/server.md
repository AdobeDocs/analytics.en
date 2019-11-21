---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# server

The  variable is used to show either the domain of a web page (to show which domains people come to) or the server serving the page (for a load balancing quick reference).


<!-- 

server.xml

 -->

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | server  | Servers  | ""  |

If your site has more than one domain serving the same content, the *`server`* variable can be used to track which of those domains visitors are using. The following JavaScript will populate the domain of the page into the server variable.

```js
s.server=window.location.hostname
```

If you are using the server variable to give a quick guide to load balancing, you could put a server name or number into the server variable. See the following example:

```js
s.server="server 14"
```

While the [!UICONTROL Most Popular Servers] report may be used as a load balancing quick reference, it is not a precise measure of server load. For example, back-button traffic does not increase server load, but is shown in reports. The report does not show which servers are serving images or large downloads.

**Syntax and Possible Values** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**Examples** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 

```

**Configuration Settings** {#section_969DB379D5BD469FBEE8D505D3000E49}

None

**Pitfalls, Questions, and Tips** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

