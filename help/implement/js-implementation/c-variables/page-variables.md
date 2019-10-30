---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
seo-description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
seo-title: Page variables
solution: Analytics
subtopic: Variables
title: Page variables
topic: Developer and implementation
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
---

# Page variables

Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

The  variable displays the height of the browser window.

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

**Parameters** 

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Query Param </th> 
   <th class="entry"> Value </th> 
   <th class="entry"> Example </th> 
   <th class="entry"> Reports Affected </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>A positive integer </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Traffic &gt; Technology &gt; Browser Height </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

The  variable displays the width of the browser window.

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

**Parameters** 

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Query Param</b> </p> </td> 
   <td> <p> <b>Value</b> </p> </td> 
   <td> <p> <b>Example</b> </p> </td> 
   <td> <p> <b>Reports Affected</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>A positive integer </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Traffic &gt; Technology &gt; Browser Width </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

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

* The [!UICONTROL getQueryParam] plug-in, used in the JavaScript file, retrieves a query string parameter from the URL. For more information on the [!UICONTROL getQueryParam] plugin, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Assign a value to the *`campaign`* variable in the HTML on the Web page.

With either method of populating the *`campaign`* variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.

For example, a visitor enters your site by clicking a paid search keyword. When the visitor arrives on the landing page, the URL contains a query string parameter identifying the tracking code for the keyword. The visitor then clicks a link to another page, but then immediately clicks the Back button to return to the landing page. When the visitor arrives a second time on the landing page, the URL with the query string parameter identifies the tracking code again. And a second click-through is registered, thereby falsely inflating the number of click-throughs.

To avoid this inflation of click-throughs, Adobe recommends using the [!UICONTROL getValOnce] plugin to force each campaign click-through to be counted only once per session. For more information on the [!UICONTROL getValOnce] plugin, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

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

* To keep click-throughs from being inflated, use the [!UICONTROL getValOnce] plugin to let the click-through for a campaign be counted only once per session. For more information on the [!UICONTROL getValOnce] plug-in, see [Implementation Plug-ins](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* For more information on tracking marketing campaigns and keyword buys, see [Campaigns](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use the [!DNL DigitalPulse Debugger] to see the actual value of campaigns (v0 in the debugger). If v0 does not appear in the debugger, no campaign data is recorded for that page.

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

The  variable is most often used to identify a section of your site.

<!-- 

channel.xml

 -->

For example, a merchant may have sections such as Electronics, Toys, or Apparel. A media site may have sections such as News, Sports, or Business.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 Bytes  | CH  | Site Content > Site Sections  | ""  |

Adobe recommends populating the channel variable on every page. You can also turn on a correlation between the *`channel`* and [!UICONTROL page name] variables.

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**Syntax and Possible Values** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**Examples** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Pitfalls, Questions, and Tips** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

The  variable is used to show the number of bits used to display color on each pixel of the screen.

<!-- 

colordepth.xml

 -->

For example, 32 represents 32 bits of color on the screen. This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  c  | 8,16, and 32  | 32  | Traffic > Technology > Monitor Color Depth  |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

The  variable, in Internet Explorer, indicates whether the browser is configured on a LAN or modem connection.

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  ct  | lan or modem  | lan  | Traffic > Technology > Connection Type  |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

The  variable indicates whether a first-party session cookie could be set by JavaScript.

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into `props/eVars`, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  |
|---|---|---|
|  k  | Y or N  | Y  |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Deprecated) The  variable lets you select the data center to which your data is sent.

<!-- 

dc.xml

 -->

> [!NOTE] The dc variable is deprecated. You should set *`trackingServer`* for all implementations to the value that is generated by [!UICONTROL Code Manager] in s_code.js.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | 112  |

The data center is identified in the *`dc`* variable in order to match [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

The [!UICONTROL eVar] variables are used for building custom reports.

<!-- 

eVarN.xml

 -->

When an eVar is set to a value for a visitor, the value is remembered until it expires. Any success events that a visitor encounters while the eVar value is active are counted toward the eVar value.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  255 Bytes  | V1-v75 ( [or v100 or v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28))  | Custom Conversion  | ""  |

**Expiration** {#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVars] expire after a time period you specify. After the eVar expires, it no longer receives credit for success events. eVars can also be configured to expire on success events. For example, if you have an internal promotion that expires at the end of a visit, the internal promotion receives credit only for purchases or registrations that occur during the visit in which they were activated.

There are two ways to expire an eVar:

* You can set the eVar to expire after a specified time period or event.
* You can use force the expiration of an eVar, which is useful when repurposing a variable.

If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. Doing so will help keep internal promotion values out of June's reports.

**Case Sensitivity** {#section_6E9145B7FCC2438E95BB35AAE3857412}

eVars are case insensitive, but they are displayed in the capitalization of the first occurrence. For example, if the first instance of eVar1 is set to "Logged In," but all subsequent instances are passed as "logged in," reports always show "Logged In" as the value of the eVar.

**Counters** {#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

While eVars are most often used to hold string values, they may also be configured to act as counters. eVars are useful as counters when you are trying to count the number of actions a user takes before an event. For example, you may use an eVar to capture the number of internal searches before purchase. Each time a visitor searches, the eVar should contain a value of '+1.' If a visitor searches four times before a purchase, you will see an instance for each total count: 1.00, 2.00, 3.00, and 4.00. However, only the 4.00 receives credit for the purchase event (Orders and Revenue Metrics). Only positive numbers are allowed as values of an eVar counter.

**Subrelations** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

A common requirement for a [!UICONTROL Custom eVar] report is the ability to break down one [!UICONTROL Custom eVar] report by another. For example, if one eVar contains gender, and another contains salary, you may ask the following question: of the female visitors to my site, how much revenue was generated by women who make more than $50,000 per year. Any eVar that is fully sub-related allows this type of break down in reports. For example, if the gender eVar has full subrelations enabled, all other custom eVar reports can be broken down by gender, and gender can be broken down by all others. To see the relationship between two reports, only one of them needs full subrelations enabled. By default, [!UICONTROL Campaigns], [!UICONTROL Products], and [!UICONTROL Category] reports are fully sub-related (any eVar can be broken down by campaign or products).

**Syntax and Possible Values** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

When not used as a counter, eVars have the same limitations as all other variables. If the eVar is a "counter," it is expected to receive numeric values like "1" or "2.5." If more than two decimal places are given, the eVar counter rounds to two decimal places. An eVar counter may not contain negative numbers.

**Examples** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Configuration Settings** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVars can be configured in [!UICONTROL Analytics > Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]. All eVars can be configured with a [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Allocation], [!UICONTROL Expire After Setting], or [!UICONTROL Reset]. Each configuration setting is addressed separately.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Setting </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Name </td> 
   <td> Allows you to change the name of the eVar report within <span class="keyword"> Analytics </span>. <p>The eVar should still be referenced as s.eVarX in the JavaScript code, no matter what name is given to the report in <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type </td> 
   <td> Allows you to show whether the eVar is a Text String or Counter. </td> 
  </tr> 
  <tr> 
   <td> Allocation </td> 
   <td> Used to configure which value of the eVar receives credit for success events. <p>If Allocation is set to "Most Recent (Last)," then B receives credit. </p> <p>If Allocation is set to "Original Value (First)" then A receives credit. </p> <p>If Allocation is set to "Linear", then both A and B receive credit for half the purchase value. </p> </td> 
  </tr> 
  <tr> 
   <td> Expire After </td> 
   <td> Lets you determine whether an eVar expires on a specific event, like purchase, or after a custom or predefined time period. </td> 
  </tr> 
  <tr> 
   <td> Reset </td> 
   <td> By selecting the <span class="wintitle"> Reset </span> check box for an eVar, and clicking <span class="wintitle"> Save </span> at the bottom of the page, all values of that eVar are immediately expired. After this happens, only new values of the eVar receive credit for success events. </td> 
  </tr> 
 </tbody> 
</table>

**Pitfalls, Questions, and Tips** {#section_DA6912C802E445F986C6DE4234C6C737}

* Unlike [!UICONTROL prop] variables, eVar variables are not allowed to be lists of delimited values. If you populate an eVar with a list of values, for example "one,two,three," then that exact string appears in reports.
* eVar counters may not contain negative numbers.

## Events {#concept_FFD115543D54401B98FE683BD7D5B3FE}

The  variable is used to record common shopping cart success events as well as custom success events.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
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
   <td> No Limit </td> 
   <td> events </td> 
   <td> <p>Shopping Cart Events </p> <p>Custom Events </p> </td> 
   <td> N/A </td> 
  </tr> 
 </tbody> 
</table>

An [!UICONTROL event] should be considered a milestone within a site. Success events are most commonly populated on the final confirmation page of a process, such as a registration process or newsletter sign-up. Custom events are defined by populating the events variable with the literal values defined in the Possible Values section below.

By default, success events are configured as *counter* events. Counter events count the number of times a success event is set (x+1). Events can also be configured as *numeric* events. Numeric events allow you to specify the number to increment (as might be necessary when counting dynamic or arbitrary values, such as the number of results returned by an internal search).

A final event type, *currency*, allows you to define the amount to be added (similar to numeric events), but displays as currency in reports, and is subject to currency conversions based on the s. *`currencyCode`* value and the default currency setting for your report suite. For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configuring the Variable** {#section_9195286C34C54B02B2598E2B856492C3}

The [!UICONTROL s.events] variable is enabled by default for all implementations. The seven pre-configured conversion events are automatically enabled for all new report suites. New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

**Possible Values** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

The following is a list of possible values for the events variable: 

|  Event  | Description  | Reports Populated  |
|---|---|---|
|  prodView  | Product Views  | Products  |
|  scOpen  | Open / Initialize a new shopping cart  | Carts  |
|  scAdd  | Add item(s) to the shopping cart  | Cart Additions  |
|  scRemove  | Remove item(s) from the shopping cart  | Cart Removals  |
|  scView  | View shopping cart  | Cart Views  |
|  scCheckout  | Beginning of the checkout process  | Checkouts  |
|  purchase  | Completion of a purchase (order)  | Orders  |
|  event1 - event1000 (event100 for point product)  | Custom events  | Custom Events  |

**Syntax and Examples** {#section_45A159DF00114066B8551DDEB15E084C}

Counter events are set by placing the desired events in the [!UICONTROL s.events] variable, in a comma-separated list (if multiple events are to be passed).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

If on H23 code or higher, counter events can have integers greater than one assigned to them.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Implementing counter events with assigned integer values treat the event as if it fired multiple times within the image request. Counter events do not allow decimals- it is recommended to use numeric events instead if this functionality is required.
Numeric and currency events must be included in the [!UICONTROL s.events] variable, though they typically receive their numerical value (e.g., 24.99) in the [!UICONTROL s.products] variable. This allows you to tie specific numeric and currency values to individual product entries.

**Event Serialization** {#section_A89488EF4471405AAFC4D6DD05E77621}

By default, an event is counted every time the event is set on your site.

See [Event Serialization](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) for more information.

**Syntax** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Examples** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

The [!UICONTROL hierarchy] variable determines the location of a page in your site's hierarchy.

<!-- 

hierN.xml

 -->

This variable is most useful for sites that have more than three levels in the site structure. For example, a media site may have 4 levels to the Sports section: Sports, Local Sports, Baseball, and Red Sox. If someone visits the Baseball page, Sports, Local Sports, and Baseball, all levels reflect that visit.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  255 Bytes  | H1-H5  | Hierarchy  | ""  |

There are five [!UICONTROL hierarchy] variables available, which must be enabled by Adobe Customer Care. At the time the hierarchy is enabled, you should decide on a delimiter for the variable and the maximum number of levels for the hierarchy. For example, if the delimiter is a comma, the sports hierarchy may display as follows.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Make sure that none of your section names have the delimiter in them. For example, if one of your sections is called "Coach Griffin, Jim," then you should choose a delimiter other than comma. Each hierarchy section is limited to 255 bytes, while the total variable limit is 255 bytes. After a delimiter is chosen (at the time the hierarchy is created) it is not easily changed.

Contact Adobe Customer Care about changing the delimiter for an existing hierarchy. Delimiters may also consist of multiple characters, such as || or /|\, which are less likely to appear in a hierarchy section.

**Syntax and Possible Values** {#section_0739948A68A2420DAB1CBEA3115A5A66}

Do not put a space between each delimiter. In the following example syntax, N is a number between one and five.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Do not use the delimiter except to delimit the levels of the hierarchy. The delimiter may be any character or characters of your choice.

**Examples** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Configuration Settings** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

None

**Pitfalls, Questions, and Tips** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* The delimiter may not be changed after the hierarchy is set up. If the delimiter for your hierarchy must be changed, contact Adobe Customer Care.
* The number of levels may not be changed after the hierarchy is set up.

> [!NOTE] Changes to hierarchies can result in a service charge.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

The  variable, in Internet Explorer, indicates whether the current page is set as the user's home page.

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  hp  | Y or N  | Y  | Traffic > Technology > Home Page  |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

The  variable indicates whether Java is enabled on the browser.

<!-- 

javaEnabled.xml

 -->

This variable is populated after the page code and before doPlugins is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  v  | Y or N  | Y  | Traffic > Technology > Java  |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

The  variable indicates the version of JavaScript supported by the browser.

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  j  | 1.0, 1.1, 1.2, … 1.7  | 1.7  | Traffic > Technology > JavaScript Version  |

Version H.10 and higher of the JavaScript file accurately detect up to version 1.7 (the highest version at the time H.10 was released). Prior versions of the JavaScript file only detected up to version 1.3 

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 bytes </td> 
   <td> pev2 </td> 
   <td> <p>File Downloads </p> <p>Custom Links </p> <p>Exit Links </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Custom Links] refer to links that send tracking data. The *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**Syntax and Possible Values** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**Examples** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Configuration Settings** {#section_F15FF429FC274F708D50DF79D4668EA3}

None

**Pitfalls, Questions, and Tips** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

The  variable is an optional variable used in link tracking that determines which report a link name or URL appears (custom, download, or exit links).

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> One character </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>File Downloads </p> <p>Custom Links </p> <p>Exit Links </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Custom links send data to Analytics. The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

For exit and download Links, the *`linkType`* variable is automatically populated depending on whether the link clicked is an exit or download link. A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. By setting *`linkType`* to 'o,' 'e,' or 'd,' the *`linkName`* or link URL is sent to the [!UICONTROL Custom Links], [!UICONTROL Exit Links], or [!UICONTROL File Downloads] report respectively.

**Syntax and Possible Values** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

If you are using XML, the variable may only contain a single character, namely 'o,' 'e,' or 'd.'

```js
s.tl(this,'o','Link Name');
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**Examples** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 

```

**Configuration Settings** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

None

**Pitfalls, Questions, and Tips** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* If *`linkType`* is not specified, custom links ('o') is assumed.

## List Props {#concept_83ED74232225431F83A796E22FFC75B4}

List props are a delimited list of values that are passed into a variable, then reported as individual line items. List props are most commonly implemented on pages that contain user-selectable values, such as listed items with check boxes or radio buttons. They are useful in any circumstance where you want to define multiple values in a variable without sending multiple image requests.

<!-- 

list_props.xml

 -->

**Considerations**

* List props are enabled only on traffic variables ( [props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* Pathing and correlations cannot be enabled for list props.
* Analytics provides visits and unique visitors to almost every report, including all list prop reports.
* Classifications are supported for list props.
* Any custom traffic variable can become a list prop. (Exceptions: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D), and [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2).) 

* When defining duplicate values in the same image request, instances are not deduplicated.

A prop can be changed into a list prop on the Admin Tools > Report Suite > Traffic Variables page by enabling List Support and then selecting a delimiter. Popular delimiters are colons, semi-colons, commas, or pipes. The delimiter can technically be any of the first 127 ASCII characters.

**Implementation Examples** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

When you request enabling of list props, indicate the delimiter that you would like to use. After the *`s.prop`* of your choice is enabled, multiple values can be set in the variable as shown in the following examples:

A list prop delimited by a pipe, passing in two values:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

A list prop delimited by a comma passing in several values:

```js
s.prop2="cerulean,vermilion,saffron"
```

List props can also be sent with a single value:

```js
s.prop3="Single value"
```

The delimiter can be changed at any time. However, the implementation must match the new delimiter. Failure to use the correct delimiter results in the list prop value being treated as a single concatenated line item in reporting.

Because a list prop is still a Traffic Variable, it is subject to Traffic Variable limitations. List props are limited to 100 bytes of data and are affected by case sensitivity settings.

## List Variable {#concept_AC42F2D69B674C02A484137CE5B4E687}

Also known as List Var. Similar to how List Props function, List Vars allow multiple values within the same image request. They also act similarly to eVars, which persist beyond the image request they were defined on. You can use these variables to see cause and effect among multiple elements on a single page, such as product lists, wish lists, lists of search refinements, or lists of display ads.

<!-- 

listN.xml

 -->

**Considerations**

* List Vars remember their specific values by referencing the VisitorID cookie in the visitor's browser.
* A limit of 250 maximum values are stored at one time per visitor. If 250 values per visitor are exceeded, the latest 250 values are used. Expiration for these values is based on the configured expiration for the variable.
* Each delimited value can contain a maximum of 255 characters (or less if using multi-byte characters). This is the maximum length of each element.
* There is no limit to the number of characters within this variable. The only exception to this limitation is within older Internet Explorer browsers, which impose a 2083-character limitation on all URL requests.
* A total of three List Vars are available per report suite.
* Using List Vars requires H23 code or higher.
* List Vars can be classified.
* If duplicate values are defined in the same image request, list vars deduplicate all instances of those values.
* The most granular list vars can be segmented is on a hit (or page view) level. If you have a list var with three values in the same image request, any segment rules that match one value will pull all three into reporting. Conversely, if an exclude rule is defined that matches a single value, all three values are excluded.

**Configuration** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

You can access the configuration in the Admin Console and update it without Adobe Client Care having to get involved:

1. Go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** 
1. Select the report suite.
1. Click  **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

* **Name**: Each delimited value can contain a maximum of 255 characters (or less if using multi-byte characters). This is the maximum length of each element.
* **Value Delimiter**: The character used to separate values within the List Var. Most commonly these are characters such as commas, colons, pipes, or something similar.

  >[!NOTE]
  >
  >Multi-byte characters are not supported as delimiters in List Vars. The delimiter must be single byte.

* **Expiration**: Similar to eVar expiration, this determines the amount of time that can occur between the List Var and the conversion event for them to be related.

    * **At a page view or visit level**: Success events beyond the page view or visit would not link back to any values within the List Var.
    * **Based on a time period, such as day, week, month, etc**: Success events beyond the specified time period would not link back to any values within the List Var. A custom number of days can be defined as well.
    * **Specific conversion events**: Any other success events that fire after the specific event designated would not link back to any values within the List Var.
    * **Never**: Any amount of time can pass between the List Var and success event.

* **Allocation**: This setting determines how success events divide credit between values:

    * **Full**: All variable values defined prior to the variable's expiration get full credit for success events.
    * **Linear**: All variable values defined prior to the variable's expiration get credit divided credit for conversion events.
    * Variable values are never overwritten, but instead added to the values that get credit for success events.

* **Max Values**: Designates the number of active values allowed for this list variable. For example, if set to 3, only the last 3 values captured is saved and any previous values captured are discarded. Note that if multiple values for the same list var are sent in on the same hit and you have restricted using max values, each value will have the same timestamp and there is not guarantee as to which value is saved.

  A limit of 250 maximum values are stored at one time per visitor. If 250 values per visitor are exceeded, the latest 250 values are used. Expiration for these values is based on the configured expiration for the variable.

  The Max Values setting is useful to limit attribution to a specific number of values. For example, if a list var is set to "A,B,C" on the first page of a visit, then set to "X,Y,Z" on the next page, attribution is distributed to these six values based on the allocation. If you wanted to limit attribution to only "X,Y,Z", you can set max values to three.

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]** .

**Implementation Examples** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Each of the following examples use a comma for the value delimiter.

**Defining a single value within a List Var:**

```js
s.list1="Cat";
```

**Passing in multiple values:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Attributing revenue to a List Var:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

This result would show three line items with $50 each in revenue. (Top Banner Ad; Side Bar Ad; and Internal Campaign 1.) Note the total for this report deduplicates revenue, so the total would also reflect $50.

**Attributing revenue to a List Var that was set multiple times during a visit:**

**Allocation**: Full

**Expiration**: Visit 

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Page </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Page 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (not set) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Result**: All values set in the list var1 at any point during the visit (value1,value2,value3,value4,value5,value6) get full credit for the purchase.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

The s.maxDelay variable is used primarily in Genesis DFA integrations to determine the timeout period in contacting the DFA host. If Adobe does not receive a response from DFA's servers within the specified period set in the  variable, the connection is severed, and data is processed normally. Implement this variable if you are concerned with DFA's response time on each page. It is recommended to experiment with this value to determine the optimum timeout period.

<!-- 

maxDelay.xml

 -->

**Implementation Example**

```
s.maxDelay="750";
```

**Properties**

* This variable is an optional event metric populated via the JavaScript implemented on your site.
* If the DFA host does not respond within the given amount of time, the event designated to Timeout runs (assigned via the Genesis integration wizard).
* This variable can only contain a numeric value.
* The amount of time specified is measured in milliseconds.
* Increasing the wait time collects more DFA data, but also increases the risk of losing Analytics hit data.

  Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* Decreasing the wait time will lower the risk of losing Analytics hit data, but can reduce the amount of DFA data sent with hit data.

  Losing DFA integration data would occur when the *`s.maxDelay`* period does not accommodate enough time for the DFA host to respond.

> [!NOTE] Adobe does not have control over DFA's response time. If you are seeing consistent issues even after raising the max delay period to a reasonable time frame, consult your organization's DFA account administrator.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

The  variable specifies the total length of the media being played.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> No max size for entire pev3 request - size is limited to the browser's URL length limit. </td> 
   <td> pev3 </td> 
   <td> Time Spent on Video; <p>Video Segments Viewed </p> </td> 
   <td> None </td> 
  </tr> 
 </tbody> 
</table>

**Syntax and Possible Values** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the [!UICONTROL mediaLength] variable does not need to be implemented explicitly. It is determined automatically by the AppMeasurement for JavaScript code.

**Manual Tracking Method:**

Syntax: 

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Possible Values: 

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Examples** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pitfalls, Questions, and Tips** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* You must call the media tracking methods only if the player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* If not tracking using [!UICONTROL autoTrack], be sure to set the length in seconds.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

This variable specifies the name of the video or media item.

<!-- 

mediaName.xml

 -->

It is only available via the [!UICONTROL Data Insertion API] and [!UICONTROL Full Processing Data Source].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  64 KB  | pev3  | Videos; Next Video Flow; Previous Video Flow; Video Segments Viewed; Time Spent on Video  | None  |

**Syntax and Possible Values** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* variable does not need to be implemented explicitly. It is determined automatically by the AppMeasurement for JavaScript code.

**Manual Tracking Method:**

Syntax:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 

```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Possible Values:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Examples** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 

```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Pitfalls, Questions, and Tips** {#section_941A445BB52E4063B0F6920E61BB90DE}

* You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.
* This variable is stored as a mySQL TEXT variable as opposed to VARCHAR(100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

This variable specifies the player used to consume a video or media item.

<!-- 

mediaPlayer.xml

 -->

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 Bytes  | pev3  | Video Players  | None  |

**Syntax and Possible Values** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**autoTrack Method:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Manual Tracking Method:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Possible Values:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Examples** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Pitfalls, Questions, and Tips** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

You must call the media tracking methods only if player cannot be tracked using s.Media.autoTrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

This variable specifies the segments of a video or media asset consumed.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
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
   <td> 255 Bytes </td> 
   <td> pev3 </td> 
   <td> Time Spent on Video <p>Video Segments Viewed </p> </td> 
   <td> None </td> 
  </tr> 
 </tbody> 
</table>

**Syntax and Possible Values** {#section_9A63266633C4427CB4A6549E4D887B85}

**autoTrack Method:**

If using [!UICONTROL s.Media.autoTrack], the *`mediaName`* does not need to be implemented explicitly. It will be determined automatically by the AppMeasurement for JavaScript code.

**Manual Tracking Method:**

Syntax:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 

```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Possible Values:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 

```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Examples** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 

```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Pitfalls, Questions, and Tips** {#section_1BCEB037AB724B6EBE87420BD3604B88}

You must call the media tracking methods only if player cannot be tracked using [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

The  variable identifies which events should be sent with a media hit.

<!-- 

media_trackEvents.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | s.Media.trackEvents="None"  |

**Syntax and Possible Values** {#section_66A978EF56914BEAAE73359A268A1B4A}

Event names such as event1 or purchase.

**Examples** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Pitfalls, Questions, and Tips** {#section_030B11C64EE84D46A85CA550DB732D28}

Make sure to populate [!UICONTROL trackVars] with "events" whenever this variable is populated.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

The  variable identifies which variables should be sent with a media hit.

<!-- 

media_trackVars.xml

 -->

It is only applicable with JavaScript and [!UICONTROL ActionSource].

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | s.Media.trackVars="None"  |

**Syntax and Possible Values** {#section_7374684A7EB34AE685E8C40A66CFD289}

Variable names such as [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, and so forth.

**Examples** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars="prop2,events,eVar3"
```

**Pitfalls, Questions, and Tips** {#section_615AE1B696124B00B78F651B03813EAB}

* Even if eVar3 is specified in [!UICONTROL trackVars], it is sent with the media hit.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

The  variable controls the order in which cookies and subscriber IDs are used to identify visitors.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | /5/ or /1/ in path of image url  | N/A  | None  |

**Syntax and Possible Values** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 

```

**Pitfalls, Questions, and Tips** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Use cross-visitor identification to mitigate possible spikes in visitor traffic when using the *`s.mobile`* variable with the JavaScript cookie implementation.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

The  variable contains the name of each page on your site.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
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
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Pages </p> <p>Paths </p> </td> 
   <td> page URL </td> 
  </tr> 
 </tbody> 
</table>

The *`pageName`* variable should be populated with a value that business users recognize. In most cases the *`pageName`* value is not the URL or the path to the file. Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

Be careful not to allow new-line, -em or -en dashes, or any HTML characters to appear in the page name and other variables. Some browsers send new line characters while others don't, which causes the data in Analytics to be split between two seemingly identical page names. Many word processors and email clients will automatically convert a hyphen into an -en or -em dash when typing. Since -en and -em dashes are illegal characters in Analytics variables (ASCII characters with codes above 127), Analytics won't record the page name containing the illegal character and show the URL instead.

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**Syntax and Possible Values** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**Examples** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 

```

```js
s.pageName="Standard Offer List"
```

**Configuration Settings** {#section_58CBC68C805344A999EB47455FEBA8D5}

Administrators have the ability to change the visible page name in Analytics with the [!UICONTROL Name Pages] tool, which is potentially dangerous and may negatively affect your reports. Please contact Adobe Customer Care before using the [!UICONTROL Name Pages] tool.

**Pitfalls, Questions, and Tips** {#section_BB41DC9682C34385B9CAA80D5257C113}

Make sure the *`pageName`* doesn't contain illegal characters.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

The  variable is used only to designate a 404 Page Not Found Error page.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
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
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Paths &gt; Pages &gt; Pages <p>Not Found </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Set up the *`pageType`* variable on the error page exactly as shown below.

Do not use the page name variable on 404 error pages. The *`pageType`* variable is only used for the 404 Error page.

In most cases, the 404 Error page is a static page that is hard-coded. In these cases, it is important that the reference to the .JS file is set to an appropriate global or relative path/directory.

**Syntax and Possible Values** {#section_C1C59968226446559B05F6EE7374D525}

The only allowable value of *`pageType`* is "errorPage" as shown below.

```js
s.pageType="errorPage"
```

**Examples** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Configuration Settings** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

None

**Pitfalls, Questions, and Tips** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. By following this course of action, you can use [!UICONTROL Pathing] reports to see which paths caused users to generate 500 errors. The prop explains which error message is given by the server.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

The  variable overrides the actual URL of the page.

<!-- 

pageURL.xml

 -->

In rare cases, the URL of the page is not the URL that you would like reported in Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
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
   <td> No Limit* </td> 
   <td> <p>G </p> </td> 
   <td> Traffic &gt; Segmentation &gt; Most Popular Pages Paths </td> 
   <td> Page URL </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**Syntax and Possible Values** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. The domain will be forced to display in lower-case before being populated in reports, and the query string may be stripped, depending on Analytics settings.

```js
s.pageURL="proto://domain/path?query_string"
```

Only URL-compatible characters are allowed as the page URL.

> [!NOTE] It is strongly advised that you contact your Adobe consultant or Customer Care before using the *`pageURL`* variable for custom purposes.

**Examples** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 

```

```js
s.pageURL="https://www.mysite.com/"
```

**Configuration Settings** {#section_A8F77DAD88164528ACC5C16C066B47DF}

None 

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

The  variable, in Netscape and Mozilla-based browsers, lists the plugins installed on the browser.

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  p  | Recognized plugins  | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM;  | Traffic > Technology > Plugins  |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

The  variable is used for tracking products and product categories as well as purchase quantity and purchase price. Products is typically set in conjunction with a cart event or a  event.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. This update may cause an increase in *`prodView`* events. *`prodViews`* will increase only when: 
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
>
>1. The *`products`* variable is not empty.
>
>A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. For instance, the products variable can track how many times a product is viewed, added to the shopping cart, checked out, and purchased. It can also track the relative effectiveness of merchandising categories on your site. The scenarios below are common for using the products variable.

The *`products`* variable should always be set in conjunction with a success event.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
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
   <td> <p>The " <span class="wintitle"> products </span>" string has a maximum size of 64k. </p> </td> 
   <td> products </td> 
   <td> Products <p>Categories (optional) </p> <p>Revenue (optional) </p> <p>Units (optional) </p> <p>Custom Events (optional) </p> <p>eVars (optional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Syntax** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

|  Field  | Definition  |
|---|---|
|  Category  | Contains the associated product category. In version 15, products can be associated with multiple categories which fixes a limitation present in version 14. If you were previously not recording a product category, you are encouraged to start populating this field for report suites that are on version 15.  |
|  Product  | (Required) The identifier used to track a product. This identifier is used to populate the [!UICONTROL Products] report. Be sure to use the same identifier through the checkout process.  |
|  Quantity  | The number of units purchased. This field must be set with a [!UICONTROL purchase] event to be recorded.  |
|  Price  | Refers to the combined cost of the total quantity purchased (units x individual unit price), not to the individual price. This field must be set with a [!UICONTROL purchase] event to be recorded.  |
|  Events  | Currency events associated with the specified product. See [Product-Specific Currency Events](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) and [Order-Wide Currency Events](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0).  |
|  eVars  | Merchandising eVar values associated with a specific product. See [Merchandising Variables](/help/components/c-variables/c-merch-variables/var-merchandising.md).  |

The values included in the *`products`* variable are based on the type of event you are recording. The category/product delimiter (;) is required as a place holder when omitting Category. Other delimiters are required only if they are necessary to distinguish which parameter you are including, as shown in the examples on this page.

**Setting products with Non-Purchase Events** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**Setting products with a Purchase Event** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") page of the order process. The product name, category, quantity, and price are all captured in the *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**Product-Specific Currency Events** {#section_F814DF053C0D463A97DA039E6323720C}

If a currency event receives a value in the *`products`* variable instead of the events variable, it applies only to that value. This is useful to track product-specific discounts, product shipping, and similar values. For example, if you configured event 1 to track product shipping, a product with a "4.50" shipping charge might appear similar to the following:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

In this example, the value of 4.50 is associated directly with the "Running Shoes" product. If you add event1 to the products report, you'll see "4.50" listed for the "Running Shoes" line item. Similar to Price, this value should reflect the total for the quantity listed. If you have 2 items with a 4.50 shipping charge each, event1 should be "9.00".

**Order-Wide Currency Events** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

If a currency event receives a value in the events list instead of the *`products`* variable, it applies to all products in the *`products`* variable. This is useful to track order-wide discounts, shipping, and similar values, without modifying the product price or by tracking it in the product list separately.

For example, if you configured event10 to contain order-wide discounts, a purchase with a 10% discount might appear similar to the following:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

On currency event reports, the report total represents the de-duplicated event total (in this example, the total amount of discounts during the reporting period), not the sum of the event values for each product. For example, you would see "9.95" listed for both "Running Shoes" and "Running Socks", and the total would also be "9.95".

> [!NOTE] if a value for the same Numeric/Currency Event is specified in the *`products`* variable and in the *`events`* variable, the value from the *`events`* is used.

**Pitfalls, Questions, and Tips** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). If no [!UICONTROL success] event is specified, the default event is [!UICONTROL prodView].

* Strip all commas and semicolons from product and category names before populating products.
* Strip all HTML characters (registered symbols, trademarks, and so forth).
* Strip currency symbols ($) from the price.

**Examples** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

Property ( [!UICONTROL prop]) variables are used for building custom reports within the [!UICONTROL Traffic Module].

<!-- 

propN.xml

 -->

The props variable may be used as counters (to count the number of times a page view is sent), for pathing reports, or in correlation reports.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | c1-c75  | Custom Traffic  | ""  |

**Syntax and Possible Values** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

There are no limitations on [!UICONTROL property] variables outside of the standard variable limitations.

**Examples** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 

```

```js
s.prop15="toy category"
```

**Configuration Settings** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contact Adobe Customer Care about showing [!UICONTROL Visit], [!UICONTROL Visitor], and [!UICONTROL Path] metrics for [!UICONTROL prop] variables.

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

The  is used to keep an order from being counted multiple times in reporting.

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  20 bytes  | purchaseID  | Conversion > Purchases > Revenue Conversion  | ""  |

When a visitor purchases an item from your site, *`purchaseID`* is populated on the "Thank You" page at the same place the [!UICONTROL purchase] event is fired. If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. This is critical because many visitors to your site will save the "Thank You" or "Confirmation Page" for their own purposes. The *`purchaseID`* keeps purchases from being counted each time the page is viewed.

In addition to keeping the purchase data from being counted twice, the *`purchaseID`*, when used, keeps all conversion data from being double counted in reports.

**Syntax and Possible Values** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**Examples** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Configuration Settings** {#section_1808631C96674380BF9C4A6D9A2C568E}

None

**Pitfalls, Questions, and Tips** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

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

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

The  variable indicates the monitor resolution of the visitor viewing the web page.

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

> [!NOTE] This variable should only be read and never set.

You may read these values and copy them into props/eVars, but you should never alter them. This variable is introduced with version H.11 of the JavaScript file.

|  Query Param  | Value  | Example  | Reports Affected  |
|---|---|---|---|
|  s  | WxH  | 1680x1050  | Traffic > Technology > Monitor Resolution  |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

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

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

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

## state {#concept_82295D22888947BF8B1C76182C635C6C}

The  and  variables are conversion variables.

<!-- 

state.xml

 -->

They are like eVars in that they capture events, but unlike eVars, they don't persist. The *`zip`* and *`state`* variables are like eVars that expire immediately.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  50 bytes  | state  | Conversion > Visitor Profile > Visitor State  | ""  |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. For conversion sites, Adobe recommends using the billing address as the source for the Zip Code, but you may choose to use the shipping address instead (assuming there is only one shipping address for the order). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntax and Possible Values** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**Examples** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 

```

```js
s.state="prince edward island"
```

**Configuration Settings** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

None

**Pitfalls, Questions, and Tips** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

This variable lets you customize the timestamp of a hit similar to the AppMeasurement libraries for other platforms.

<!-- 

timestamp.xml

 -->

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  4 bytes  | Date/Time  | Not reported directly.  | Set by data collection servers.  |

**Syntax** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>Additionally, if you enable timestamp support on a report suite to support offline tracking, all hits sent to this report suite from JavaScript must also have a timestamp manually set (using *`s.timestamp`*). You cannot send both time-stamped and non-time-stamped hits to the same report suite.
>
>You can also use the [Timestamps Optional](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)setting to mix timestamped and non-timestamped data in the same global report suite, send timestamped data from a mobile app to a global report suite, and upgrade apps to employ timestamps without having to create a new report suite.

**Timestamp Formats** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Timestamps must be in UNIX (seconds since Jan 1st 1970) or ISO-8601 format, with the following restrictions on the accepted ISO-8601 format:

* Both date and time must be provided, separated by "T" 
* The date must be a calendar date with full precision (year, month, and day). . Week dates and ordinal dates are not supported.
* The date can be in standard or extended format ( `YYYY-MM-DD` or `YYYYMMDD`), but they must include the hour and minute. Seconds are optional ( `HH:MM`, `HH:MM:SS`, `HHMM`, or `HHMMSS`). Fractional minutes and seconds can be passed in, but the fractional part is ignored.

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

UNIX timestamps continue to be supported (seconds since Jan 1st 1970).

**Examples** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

The following list contains examples of valid ISO-8601 format timestamps:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Configuration Settings** {#section_5275D206F2CB4009B3681E8C4457124A}

A report suite must be enabled to accept custom timestamps by Customer Care before you can use this variable. After custom timestamps are enabled, all hits sent to the report suite must contain a timestamp or they are discarded.

**Pitfalls, Questions, and Tips** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Timestamps are primarily used to track offline data on mobile platforms. Custom timestamps are typically disabled unless you are collecting both web and offline app data in the same report suite.
* Data is timestamped when offline data is enabled in the mobile SDK (default setting) or anytime a report suite is configured to accept time-stamped data. Data collected offline on mobile devices may be sent hours or weeks after the date when it happened. These hits may be queued within the Analytics platform for minutes or hours longer than hits without timestamps:

    * For time-stamped data sent in very near current time, the probable delay is 10-15 minutes.
    * For time-stamped data sent in from yesterday, the probable delay is about 2 hours.
    * For time-stamped data sent in that is older than yesterday, every day adds about 1 hour of delay, up to 15 days ago, when the delay stops going up.

* Timestamp-enabled session data is kept for up to 92 days.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

The  variable is used for first-party cookie implementation to specify the domain at which the image request and cookie is written.

<!-- 

trackingServer.xml

 -->

Used for non-secure pages. If *`trackingServer`* is defined, nothing goes to 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | ""  |

A list of Adobe data centers can be found [here](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

The  variable is used for first-party cookie implementation to specify the domain at which the image request and cookie is written.

<!-- 

trackingServerSecure.xml

 -->

Used for secure pages. If *`trackingServerSecure`* is not defined, SSL data goes to *`trackingServer`*.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | ""  |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL Integration Data Sources] use a [!UICONTROL transaction ID] to tie offline data to an online transaction (like a lead or purchase generated online).

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. See [Data Sources](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  100 bytes  | xact  | n/a  | ""  |

**Enable Transaction ID Storage** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. This setting is located at 

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

To see whether *`transactionID Storage`* is enabled for a report suite, go to

```
Analytics > Admin > Data Sources > Manage
```

**Syntax and Possible Values** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. If multiple [!UICONTROL transactionIDs] should be recorded in a single hit, you can use a comma to delimit multiple values.

**Examples** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Pitfalls, Questions, and Tips** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* If *`transactionID`* recording is not enabled, *`transactionID`* values will be discarded and unavailable for use with [!UICONTROL Integration Data Sources]. Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. Otherwise, no data is recorded for the *`transactionID`*.

* If you are recording [!UICONTROL transactionIDs] for multiple systems, such as purchases and leads, make sure the value in *`transactionID`* is always unique. This can be accomplished by adding a prefix to the ID, such as lead_1234 and purchase_1234. [!UICONTROL Integration Data Sources] do not function as expected ( [!UICONTROL Data Source] data will tie to the wrong data) if a unique *`transactionID`* is seen twice.

* By default, *`transactionID`* values are remembered for 90 days. If your offline interaction process is longer than 90 days, contact Customer Care to have the limit extended.

> [!NOTE] The *`transactionID`* variable can contain any character other than a comma. It should be in the same location where the character limit (100 bytes) is specified. If multi-byte characters are used, multi-byte character support must be enabled in order to avoid problems with unexpected characters in the *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

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

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

The  variable is used to identify the domain with which cookies are set.

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. Visitor history becomes disconnected from current and future traffic. Do not alter this variable without approval from an Adobe representative.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | ns  | N/A  | ""  |

Analytics uses a cookie to uniquely identify visitors to your site. If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. All visitors to your site should have their cookies associated with the same domain or sub-domain.

The reason for using the *`visitorNamespace`* variable is to avoid the possibility of overloading a browser's cookie limit. Internet Explorer imposes a limit of 20 cookies per domain. By using the *`visitorNamespace`* variable, other companies' Analytics cookies will not conflict with your visitors' cookies.

**Syntax and Possible Values** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**Visitor Identification across Report Suites** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. If you specify `visitorNamespace`, the same `s_vi` cookie will be used for all report suites that send data to the specified `trackingServer`. If you have implemented multi-suite tagging, make sure you specify the visitor namespace so the same cookie is used by each report suite.  

**Examples** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Configuration Settings** {#section_1128A2531ECC43DFA6749ECC21F050A2}

None 

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

The  and  variables are conversion variables.

<!-- 

zip.xml

 -->

They are like eVars in that they capture events, but unlike eVars, they don't persist. The *`zip`* and *`state`* variables are like eVars that expire immediately.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  50 bytes  | zip  | Conversion > Visitor Profile > ZIP/Postal Codes  | ""  |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe recommends using the billing address as the source for the Zip Code. You may choose to use the shipping address instead (assuming there is only one shipping address for the order). A media site may choose to use *`zip`* and *`state`* for registration or ad click-through tracking.

**Syntax and Possible Values** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**Examples** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Configuration Settings** {#section_7987084EECC34DD38B643B94F82385CA}

None

**Pitfalls, Questions, and Tips** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Populate [!UICONTROL zip] on every page in which a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

