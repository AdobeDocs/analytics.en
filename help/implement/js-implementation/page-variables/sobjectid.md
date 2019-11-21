---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# s_objectID

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.


<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

> [!NOTE] A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 Bytes  | OID  | [!UICONTROL Activity Map], [!UICONTROL ClickMap]  | The Absolute URL of a Clicked Link  |

There are three common reasons to use *`s_objectID`*:

* To aggregate visitor activity that changes often during a day.
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**Aggregate Clicks on Highly Dynamic Links** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

If your site is highly dynamic, and links on some pages change throughout the day, *`s_objectID`* may used to identify the location of a link on the page. If *`s_objectID`* is set to "top left 1" or "top left 2," which represents the first link in the top left of the page for example, then all links that appear in that location (or that have *`s_objectID`* set to the same value) are reported together with visitor click map. If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**Separate Clicks Combined** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

If the *`pageName`* variable on your site is used to show the section or template a visitor is viewing, rather than the specific page the visitor is viewing, you may want to use *`s_objectID`* to separate links that appear on multiple versions of that page template. For example, if you have a template page for all products on your site, it is likely that there is a link to your home page and to a search box from that template on all pages. If you want to see how those links are used on an individual product basis (rather than a template basis), you can populate *`s_objectID`* with a product specific value such as "prod 123789 home page" or "prod 123789 search." Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**Improve [!UICONTROL Activity Map] Accuracy** {#section_08B3406821294DCCABEEB99C90CF5C52}

In some cases, browsers other than Internet Explorer, Firefox, Netscape, Opera, and Safari are not reported. Although this is a small percentage, it accounts for some clicks and other metrics. Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. The following is an example of how to update your links to use *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 

```

**Syntax and Possible Values** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID may contain any text identifier.

```js
s_objectID="unique_id" 

```

There are no limitations on *`s_objectID`* outside of the standard variable limitations.

**Examples** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 

```

```js
s_objectID="prod 123789 search"
```

**Configuration Settings** {#section_95396657D55B41ECB66B83D0534EA827}

None 
