---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---


# campaign

The  variable identifies marketing campaigns used to bring visitors to your site. The value of  is usually taken from a query string parameter.

<!-- 

campaign.xml

 -->

**Parameters** 

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Max Size </th> 
   <th class="entry"> Debugger Parameter </th> 
   <th class="entry"> Reports Populated </th> 
   <th class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 Bytes </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversion &gt; Campaigns &gt; Tracking Code </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Every element in a marketing campaign should have an associated unique tracking code. For example, a paid search engine keyword may have a tracking code of 112233. When someone clicks the keyword with the 112233 tracking code and is routed to the corresponding website, the *`campaign`* variable records the tracking code.

There are two main ways to populate the *`campaign`* variable:

* The [!UICONTROL getQueryParam] plug-in, used in the JavaScript file, retrieves a query string parameter from the URL. For more information on the [!UICONTROL getQueryParam] plugin, see [Implementation Plug-ins](/help/implement/js-implementation/plugins/impl-plugins.md).

* Assign a value to the *`campaign`* variable in the HTML on the Web page.

With either method of populating the *`campaign`* variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.

For example, a visitor enters your site by clicking a paid search keyword. When the visitor arrives on the landing page, the URL contains a query string parameter identifying the tracking code for the keyword. The visitor then clicks a link to another page, but then immediately clicks the Back button to return to the landing page. When the visitor arrives a second time on the landing page, the URL with the query string parameter identifies the tracking code again. And a second click-through is registered, thereby falsely inflating the number of click-throughs.

To avoid this inflation of click-throughs, Adobe recommends using the [!UICONTROL getValOnce] plugin to force each campaign click-through to be counted only once per session. For more information on the [!UICONTROL getValOnce] plugin, see [Implementation Plug-ins](/help/implement/js-implementation/plugins/impl-plugins.md).

**Syntax and Possible Values** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe recommends limiting the value to standard ASCII characters.

**Case Sensitivity** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

eVars are case insensitive, but they are displayed in the capitalization of the first occurrence. For example, if the first instance of eVar1 is set to "Logged In," but all subsequent instances are passed as "logged in," reports always show "Logged In" as the value of the eVar.

**Examples** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Configuration Settings** {#section_4083F281968443169EAF8C0E8529D7BC}

Each campaign value remains active for a user, and receives credit for that user's activities and success events until it expires. You can change the expiration of the campaign variable in the Admin Console.

**Pitfalls, Questions, and Tips** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* To keep click-throughs from being inflated, use the [!UICONTROL getValOnce] plugin to let the click-through for a campaign be counted only once per session. For more information on the [!UICONTROL getValOnce] plug-in, see [Implementation Plug-ins](/help/implement/js-implementation/plugins/impl-plugins.md).

* For more information on tracking marketing campaigns and keyword buys, see [Campaigns](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use the [!DNL DigitalPulse Debugger] to see the actual value of campaigns (v0 in the debugger). If v0 does not appear in the debugger, no campaign data is recorded for that page.
