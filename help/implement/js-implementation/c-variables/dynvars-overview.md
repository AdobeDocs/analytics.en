---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
seo-title: Dynamic variables
solution: Analytics
subtopic: Variables
title: Dynamic variables
topic: Developer and implementation
uuid: 6002fde3-0175-468b-b348-e945050e926f
index: y
internal: n
snippet: y
---

# Dynamic variables

Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.

Dynamic variables are used when capturing the same data (for example, campaign tracking codes) in multiple variables concurrently. This is a common practice in cases where different reports offer unique and important metrics. For example, capturing internal search keywords in a [!UICONTROL Custom Conversion] variable and in a [!UICONTROL Custom Traffic] variable lets you view the [!UICONTROL Revenue] and the [!UICONTROL Weekly Unique Visitors] metrics associated with these keywords, respectively.

Dynamic variables are also useful for viewing data under various reporting conditions. A campaign tracking code can be captured in multiple eVars with various allocation and cookie expiration settings. This lets users choose the way they want to attribute conversion metrics to these campaigns.

>[!NOTE]
>
>Dynamic variables are not supported in conjunction with cookies (s_cc, s_sq, s_fid, s_vi and any cookie that is set by a plugin). You can not use D=<cookie value>.

A significant benefit of dynamic variables is the ability to capture long strings of data in multiple variables without actually passing the long string repeatedly. Some browsers limit the maximum length of HTTP GET requests (including the Adobe image request). Using dynamic variables ensures that all data is captured by reducing the length of the request to Adobe servers in cases where data is duplicated across several variables.

In the Adobe image request that occurs on the page view, if you are using dynamic variables to copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1], you would see `v1=D=c1`. If eVar1 received a value previously in the request, Adobe's servers dynamically copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1] during data processing. As a result, the value originally passed using [!UICONTROL Custom Traffic 1] also appears in the [!UICONTROL Custom Conversion 1] reports.

Dynamic variables are passed by setting a variable to the desired value and then setting other variables to `D=[variable abbreviation]`. For abbreviations for each variable, see [Data Collection Query Parameters](../../js-implementation/data-collection/data-collection.md#concept_2F280ECF4205465FA9B5D773046C1A15). Dynamic variables can pull data from the following locations:

* Other query-string variables 
* HTTP headers (except for the Cookie HTTP header)

To create a dynamic variable, add a special prefix to the start of the value. The default prefix is "D=". There are two methods of flagging dynamic variables:

* Use a default prefix of D= (For example: s.prop1="D=User-Agent" ) 
* For non-JavaScript implementations, you can define a custom prefix using the "D" query-string parameter. For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

The variable abbreviation used must match the variable parameter name passed in the image request. Some variables have multiple accepted parameters used in different cases. For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

The following information applies to dynamic variables:

* Dynamic variables work with all versions of [!DNL AppMeasurement] code. 
* Dynamic variables are case sensitive. 
* Dynamic variables support literal strings contained in quotes. 
* Dynamic variable replacement occurs before processing rules, VISTA, and other processing. 
* The dynamic variable prefix "D=" must be at the start of the variable value not in the middle. For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` . 

* As with all implementation techniques, Adobe strongly recommends testing dynamic variable implementations heavily in a development environment before deploying to production. Because the full strings that are copied are not visible in client-side debugging tools, review the affected [!DNL Analytics] reports to confirm successful implementation. 
* When copying values between variables with different maximum lengths, note that copying a value that exceeds the maximum length of the destination variable causes truncation. For example, [!UICONTROL Custom Traffic] variables have 100-character limits and [!UICONTROL Custom Conversion] variables have 255-characters limits. When copying a 150-character value from [!DNL s.eVar1] to [!DNL s.prop1] using dynamic variables, this value is truncated in the [!UICONTROL Custom Traffic] report at 100 characters.

## Dynamic Variable Examples {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Examples of dynamic variables you can use in [!DNL Analytics].

In the Adobe image request that occurs on the page view, if you are using dynamic variables to copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1], you would see `v1=D=c1`. If eVar1 received a value previously in the request, Adobe's servers dynamically copy the value of [!UICONTROL Custom Traffic 1] to [!UICONTROL Custom Conversion 1] during data processing. As a result, the value originally passed using [!UICONTROL Custom Traffic 1] also appears in the [!UICONTROL Custom Conversion 1] reports.

Note that the `D=[variable]` value should be in quotes. The [!DNL Analytics] code treats this as a string. The string will be URL encoded when passed into [!DNL Analytics] (as you will see if viewing the request in the [!DNL DigitalPulse Debugger] or a similar utility). This is normal. Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>When using the image request to track links, the type of link (download=lnk_d, exit=lnk_e, or custom link=lnk_o) must be defined, as does the Link URL/Name (pev2). Links require manual implementation by inserting code within the <a href> tag.

>[!NOTE]
>
>Dynamic variables are not supported in conjunction with cookies (s_cc, s_sq, s_fid, s_vi and any cookie that is set by a plugin). You can not use D=<cookie value>.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> JavaScript Example </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      s.eVar1="D=pageName" 
    </codeblock> </td> 
   <td colname="col2"> <p>Captures the pageName value in eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      s.prop1='D=v2+":"+c2'&amp;nbsp; 
    </codeblock> </td> 
   <td colname="col2"> <p>Concatenates eVar2:prop2 into prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      s.prop1=s.eVar1="D=g"&amp;nbsp; 
    </codeblock> </td> 
   <td colname="col2"> <p>Passes the page URL into both prop1 and eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      s.eVar1="D=v0" 
    </codeblock> </td> 
   <td colname="col2"> <p>Captures the campaign in eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      &amp;nbsp;s.prop1='D=User-Agent+"&amp;nbsp;-&amp;nbsp;"+Accept-Language' 
    </codeblock> </td> 
   <td colname="col2"> <p>Concatenates the user agent and accept language headers in prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      s.prop1="D=User-Agent" 
    </codeblock> </td> 
   <td colname="col2"> <p>Captures the user agent in prop1, </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Image Request Example </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~v0 
     
/b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~campaign 
     
/b/ss/rsid/?gn=Home&amp;c1=D%3dv0%3d&nbsp;is 
     
/b/ss/rsid/?gn=Home&amp;c1=%5b%5bv0%5d%5d%5b

    </codeblock> </td> 
   <td colname="col2"> <p>Four ways to set prop1 to a campaign </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c2=~~x-up-subno 
    </codeblock> </td> 
   <td colname="col2"> <p> Pulls the x-up-subno header into prop2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      &amp;c1=D%3DUser-Agent 
    </codeblock> </td> 
   <td colname="col2"> <p> Makes prop1 a dynamic variable filled in with the HTTP header User-Agent </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      &amp;c1=D%3D%22test%22 
    </codeblock> </td> 
   <td colname="col2"> <p> Makes prop1 a dynamic variable filled in with the string "test". This becomes more useful when used with concatenation which utilizes the + operator. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      &amp;c1=D%3D%22US%3A%20%22%2BUser-Agent 
    </codeblock> </td> 
   <td colname="col2"> <p> Makes prop1 a dynamic variable filled in with the User-Agent prefixed by "UA:" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <codeblock class="syntax javascript">
      &amp;vid=D%3DX-TM-ANTID 
    </codeblock> </td> 
   <td colname="col2"> <p> This example searches for a unique header, which in this case is X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>

