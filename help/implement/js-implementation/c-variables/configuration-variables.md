---
description: Configuration variables set in the AppMeasurement.js.
keywords: Analytics Implementation
seo-description: Configuration variables set in the AppMeasurement.js.
seo-title: Configuration variables
solution: Analytics
subtopic: Variables
title: Configuration variables
topic: Developer and implementation
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
index: y
internal: n
snippet: y
---

# Configuration variables

Configuration variables set in the AppMeasurement.js.

## Configuration variables {#concept_8FCA630706334F54B4DCB607378BCD00}

Configuration variables set in the AppMeasurement.js. 

Configuration variables control the way data is captured and processed in reporting. The most-common configuration variables that are typically set in the main global JavaScript ( [!DNL AppMeasurement.js]). These variables can be set within the Reports & Analytics page-level code and links when appropriate.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** > **[!UICONTROL Code Manager]**. Some of these configuration variables may not be applicable to your site's implementation needs.

Some of the goals of using these configuration variables are:

* Track multiple sites/domains. 
* Use any currency on purchases. 
* Capture data indifferent languages. 
* Link tracking (number of downloaded files, links to external sites. 
* Track custom links for unique purposes.

>[!NOTE]
>
>AppMeasurement requires that all configuration variables are set before the initial call to the track function, *`t()`*. If configuration variables are set after the call to *`t()`*, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the *`doPlugins`* function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!-- 

s_account.xml

 -->

The  variable determines the report suite where data is stored and reported. 

If sending to multiple report suites (multi-suite tagging), *`s.account`* may be a comma-separated list of values. The report suite ID is determined by Adobe.

**Parameters** 

<table id="table_29A59379669144A0B56C0F436B372861"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Max Size </th> 
   <th colname="col2" class="entry"> Debugger Parameter </th> 
   <th colname="col3" class="entry"> Reports Populated </th> 
   <th colname="col4" class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>40 Bytes </p> </td> 
   <td colname="col2"> <p>In the URL path </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
   <td colname="col4"> <p>N/A </p> </td> 
  </tr> 
 </tbody> 
</table>

Each report suite ID must match the value created in the [!DNL Admin Console]. Each report suite ID must be 40 bytes or less, but the aggregate of all report suites (the entire comma-separated list) has no limit.

The report suite is the most fundamental level of segmentation in reporting. You can set as many report suites as your contract allows. Each report suite refers to a dedicated set of tables that are populated in Adobe's collection servers. A report suite is identified by the *`s_account`* variable in your JavaScript code.

Within [!DNL Analytics], the site drop-down box in the upper left of the reports displays the current report suite. Each report suite has a unique identifier called a report suite ID. The *`s_account`* variable contains one or more report suite IDs to which data is sent. The report suite ID value, which is invisible to [!DNL Analytics] users, must be provided or approved by Adobe before you use it. Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The *`s_account`* variable is normally declared inside the JavaScript file (s_code.js). You can declare the *`s_account`* variable on the HTML page, which is a common practice when the value of *`s_account`* may change from page to page. Because the *`s_account`* variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If *`s_account`* does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of *`s_account`* in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of *`s_account`* also appears in the domain, before 112.2o7.net. The value in the path is the only value that determines the destination report suite. The bold text below shows the report suites that data is sent to, as it appears in the debugger. See [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
http://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Syntax and Possible Values {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

The report suite ID is an alphanumeric string of ASCII characters, no more than 40 bytes in length. The only non-alphanumeric character allowed is a hyphen. Spaces, periods, commas and other punctuation are not allowed. The *`s_account`* variable may contain multiple report suites, all of which receive data from that page.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of *`s_account`* must be provided or approved by Adobe.

## Examples {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configuring the Variable in Analytics {#section_7DFB2CCF02F045AFB1AD4F376638393B}

The friendly name associated with each report suite ID can be changed by Adobe [!DNL Customer Care]. The friendly name can be seen in [!DNL Analytics] in the site drop-down box in the top, left section of the screen.

## Pitfalls, Questions, and Tips {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If *`s_account`* is empty, not declared, or contains an unexpected value, no data is collected. 
* When the *`s_account`* variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs. 
* If [!UICONTROL s.dynamicAccountSelection] is set to 'True,' the URL is used to determine the destination report suite. Use the [!DNL DigitalPulse Debugger] to determine the destination report suite(s). 

* In some cases, [!DNL VISTA] can be used to alter the destination report suite. Using [!DNL VISTA] to re-route or copy the data to another report suite is recommended when using first-party cookies, or if your site has more than 20 active report suites. 

* Always declare *`s_account`* inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

<!-- 

dynamicAccountSelection.xml

 -->

The  variable lets you dynamically select the report suite based on the URL of each page.

>[!NOTE]
>
>*`dynamicAccountSelection`* does not work with custom link tracking.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | False  |

>[!NOTE]
>
>Both *`dynamicAccountList`* and *`dynamicAccountMatch`* are ignored if the *`dynamicAccountSelection`* variable is not declared or set to 'false.'

## Syntax and Possible Values {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Only 'true' and 'false' are allowed as values of *`dynamicAccountSelection`*.

## Examples {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Configuration Settings {#section_F052FA38144B4F84B015A263A8E711CF}

None

## Pitfalls, Questions, and Tips {#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). 
* Always use the [!DNL DigitalPulse Debugger] to determine which report suite is receiving data from each page.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

<!-- 

dynamicAccountList.xml

 -->

AppMeasurement for JavaScript can dynamically select a report suite to which it sends data. The  variable contains the rules used to determine the destination report suite.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | ""  |

This variable is used in conjunction with the *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in *`s_account`* is used. The rules listed in this variable are applied in a left-to-right order. If the page URL matches more than one rule, the left-most rule is used to determine the report suite. As a result, your more generic rules should be moved to the right of the list.

In the following examples, the page URL is [!DNL http://www.mycompany.com/path1/?prod_id=12345], *`dynamicAccountSelection`* is set to 'true,' and *`s_account`* is set to "mysuitecom." 

|  DynamicAccountList Value  | DynamicAccountMatch Value  | Report Suite to Receive Data  |
|---|---|---|
|  mysuite2=www2.mycompany.com;mysuite1=mycompany.com"  | window.location.host  | mysuite1  |
|  "mysuite1=path4,path1;mysuite2=path2"  | window.location.pathname  | mysuite1, mysuite2  |
|  "mysuite1=path5"  | window.location.pathname  | mysuitecom, mysuite1  |
|  "myprodsuite=prod_id"  | window.location.search?window.location.search:"?")  | myprodsuite  |

## Syntax and Possible Values {#section_7360E4354ED345E8BAAE210DBD58A7EC}

The *`dynamicAccountList`* variable is a semicolon-separated list of name=value pairs (rules). Each piece of the list should contain the following items:

* one or more report suite ID (separated by commas) 
* an equals sign 
* one or more URL filters (comma-separated)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Only standard ASCII characters should be used in the string (no spaces).

## Examples {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Configuration Settings {#section_9F99CD741BC7449B8CCC108094B2EB85}

None

## Pitfalls, Questions, and Tips {#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). 
* If the page URL matches multiple rules, the furthest rule on the left is used. 
* If no rules match, the default report suite is used. 
* If your page is saved to someone's hard drive or translated via a web-based translation engine (such as Google's translated pages), the dynamic account selection probably won't work. For more precise tracking, populate the *`s_account`* variable server-side. 
* The *`dynamicAccountSelection`* rules apply only to the section of the URL specified in *`dynamicAccountMatch`*. 

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain. 
* Use the [!DNL DigitalPulse Debugger] when trying to identify the destination report suite. The *`dynamicAccountSelection`* variable always overrides the value of *`s_account`*.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 

dynamicAccountMatch.xml

 -->

The  variable uses the DOM object to retrieve the section of the URL to which all rules in  are applied. 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Since the default value is [!DNL window.location.host], this variable is not required for [!UICONTROL Dynamic Account Selection] to work. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in *`dynamicAccountList`* are applied to the value of *`dynamicAccountMatch`*. If *`dynamicAccountMatch`* only contains [!DNL window.location.host] (default), the rules in *`dynamicAccountList`* apply only to the domain of the page. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | window.location.host  |

## Syntax and Possible Values {#section_95CD81972C22419B80A921CA137D3841}

The *`dynamicAccountMatch`* variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. However, the values listed below may be applied at any time.

```js
s.dynamicAccountMatch=[DOM object]
```

|  Description  | Value  |
|---|---|
|  Domain (default)  | window.location.host  |
|  Path  | window.location.pathname  |
|  Query String  | (window.location.search?window.location.search:"?")  |
|  Domain and Path  | window.location.host+window.location.pathname  |
|  Path and Query String  | window.location.pathname+(window.location.search?window.location.search:"?")  |
|  Full URL  | window.location.href  |

## Examples {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Configuration Settings {#section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

None

## Pitfalls, Questions, and Tips {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). 
* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in *`s_account`*). 

* When a page is translated via a web-based translation engine, such as Google, the [!UICONTROL Dynamic Account Selection] does not work as designed. For more precise tracking, populate the [!UICONTROL s_account]variable server-side.

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 

dynamicVariablePrefix.xml

 -->

The  variable allows deployment to flag variables, which should be populated dynamically. 

Cookies, request headers, and image query string parameters are available to be populated dynamically. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | D=  | Any  | D=  |

## Syntax and Possible Values {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

OR USE CUSTOM FLAG FOR DYNAMIC VARIABLES

```js
s.dynamicVariablePrefix=".."
```

## Examples {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

OR USE CUSTOM FLAG FOR DYNAMIC VARIABLES

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Pitfalls, Questions, and Tips {#section_6889908FBD78488D955F67DDB17617B1}

* Dynamic variables can be used to significantly reduce the total length of the URL by copying values into other variables. 
* Dynamic variables can be used to collect data from headers and cookies not otherwise available for data collection.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

<!-- 

charset.xml

 -->

The  variable translates the character set of the Web page into UTF-8. 

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

**Parameters** 

<table id="table_EFB03BD5E1EA4456AC8E0BE2F2641022"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Max Size </th> 
   <th colname="col2" class="entry"> Debugger Parameter </th> 
   <th colname="col3" class="entry"> Reports Populated </th> 
   <th colname="col4" class="entry"> Default Value </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>N/A </p> </td> 
   <td colname="col2"> <p>CE </p> </td> 
   <td colname="col3"> <p>N/A </p> </td> 
   <td colname="col4"> <p> <span class="codeph"> "" </span> </p> </td> 
  </tr> 
 </tbody> 
</table>

The *`charSet`* variable is used to identify the character set of the page. For more information on character sets, see the [Multi-byte Character Sets](https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/) white paper before using the charSet variable.

## Syntax and Possible Values {#section_EBC2176067A04D9E814CF78A86DC80FA}

The *`charSet`* variable may only contain one of a predefined set of values, as listed in [Multi-byte Character Sets](https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/).

```js
s.charSet="character_set"
```

## Examples {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## Pitfalls, Questions, and Tips {#section_E348298D2C634100AF62DFBA2EC446AF}

* The value of *`charSet`* must match the possible values listed in [Multi-byte Character Sets](https://marketing.adobe.com/resources/help/en_US/whitepapers/multibyte/). 

* The value of *`charSet`* should reflect the character set of the page.

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

<!-- 

currencycode.xml

 -->

The  variable determines the conversion rate to be applied to revenue. 

All monetary amounts are stored in a currency of your choice. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. 

<table id="table_F2E96CBE051E4D82AF312573ACFFB607"> 
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
   <td> N/A </td> 
   <td> cc </td> 
   <td> Conversion &gt; Purchases &gt; Revenue <p>All Conversion reports showing Revenue or monetary values </p> </td> 
   <td> "USD" </td> 
  </tr> 
 </tbody> 
</table>

If your site allows visitors to purchase in multiple currencies, you should use the *`currencyCode`* variable to make sure revenue is stored in the appropriate currency. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. As soon as data collection receives the data, it uses the current conversion rate to convert the 40 Euros to its USD equivalent.

Populating the *`currencyCode`* variable on the HTML page instead of in the JavaScript file is recommend if you sell in multiple currencies. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. You then convert all revenue before sending it into [!DNL Analytics].

Currency conversion applies to both revenue and any currency events. These are events that are used to sum values similar to revenue, such as tax and shipping. The revenue and currency events are specified in the products string. For more information on products, see [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). For more details on how currencies are managed, see [Multi-Currency Support](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/)..

## Syntax and Possible Values {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

Only the currency codes listed in [Multi-Currency Support](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/) are allowed.

## Examples {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

## Configuration Settings {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] can change the default currency setting for your report suite. When you change the base currency for a report suite, the existing revenue in the system is not converted. All new revenue values will be converted accordingly.

## Pitfalls, Questions, and Tips {#section_08A80A87B54A4861905953A6FA61FF8F}

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly. 
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics. 
* Currency events should not be used for non-currency purposes. If you need to count arbitrary or dynamic values that are not currency, use the [!UICONTROL numeric] event type. 
* When the *`currencyCode`* variable is empty, no conversion is applied.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 

cookiedomain.xml

 -->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set. 

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. For example, you could set cookies at the fully qualified page-name using:

`s.cookieDomain = window.location.hostname;` 

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 

cookiedomainperiods.xml

 -->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. This variable is also used by some plug-ins in determining the correct domain to set the plug-in's cookie. 

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain www.mysite.com, *`cookieDomainPeriods`* should be "2". For www.mysite.co.jp, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain [!DNL www.mysite.co.jp], the `s_cc` and `s_sq` cookies are created on the domain [!DNL co.jp]. Because [!DNL co.jp] is an invalid domain, almost all browsers reject these cookies. As a consequence, visitor click map data is lost, and the [!UICONTROL Visitor Profile] > [!UICONTROL Technology] > [!UICONTROL Cookies] report indicates that almost 100% of visitors reject cookies.

If *`cookieDomainPeriods`* is set to "3" but the domain contains only two periods, the JavaScript file sets the cookies on the subdomain of the site. For example, if setting *`cookieDomainPeriods`* to "3" on the domain [!DNL www2.mysite.com], the `s_cc` and `s_sq` cookies are created on the domain [!DNL www2.mysite.com]. When a visitor goes to another subdomain of your site (such as [!DNL www4.mysite.com]), all cookies set with [!DNL www2.mysite.com] cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". This variable definition correctly sets the cookies on the root domain, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274). 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | CDP  | Affects multiple reports as it controls how the visitor ID is stored and handled.  | "2"  |

>[!NOTE]
>
>Some cloud computing services are considered Top-Level Domains, which do not allow cookies to be written. (For example, [!DNL *.compute.amazonaws.com], [!DNL *.herokuapp.com], [!DNL *.googlecode.com], and so on.) If you implement on those services, you could potentially be affected by Analytics privacy setting that removes users who have blocked all cookies if you don't have your own domain set up (for example, if you're testing your implementation). In this case, any hit where the system has determined that cookies are disabled, non-functional, or inaccessible is opted out and thus excluded from reporting.

## Examples {#section_4218BE29FA5E49F58975A2094329B268}

Setting the variable manually: 

```js
s.cookieDomainPeriods = "3";
```

Several examples to dynamically set the variable if your core JavaScript file hosts both types:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

## Pitfalls, Questions, and Tips {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] > [!UICONTROL Technology] > [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct. 

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. This can cause data loss as visitors switch between subdomains. 
* The *`cookieDomainPeriods`* variable was used in deprecated implementations prior to *`trackingServer`* to set the visitor ID cookie. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 

fpCookieDomainPeriods.xml

 -->

The  variable is for cookies set by JavaScript (s_sq, s_cc, plug-ins) that are inherently first-party cookies even if your implementation uses the third-party 2o7.net or omtrdc.net domains. 

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* inherits the *`cookieDomainPeriods`* value. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") in the domain when the domain begins with "www." For example, www.mysite.com contains two periods, while www.mysite.co.jp contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for mysite.com and three for mysite.co.jp).

The AppMeasurement for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. There are at least two cookies affected by this variable, including s_sq and s_cc (used for visitor click map and cookie checking respectively). Cookies used by plug-ins such as [!UICONTROL getValOnce] are also affected. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | cookieDomainPeriods  |

## Sample Code for Setting Cookie Domain Variables {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 

```

## Syntax and Possible Values {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

## Examples {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

## Configuration Settings {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

None 

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

<!-- 

cookielifetime.xml

 -->

The  variable is used by both JavaScript and data collection servers in determining the lifespan of a cookie.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | cl  | Traffic > Technology > Cookies All visitor-related reports  | ""  |

If *`cookieLifetime`* is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookies 
* Cookies 
* JavaScript Settings and Plugins

## Syntax and Possible Values {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

The possible values are listed as follows:

* "" 
* "NONE" 
* "SESSION" 
* An integer representing the number of seconds until expiration

## Examples {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Configuration Settings {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

None

## Pitfalls, Questions, and Tips {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* affects [!DNL Analytics] tracking. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Use caution when setting *`cookieLifetime`*. 

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 

doPlugins.xml

 -->

The  variable is a reference to the  function, and allows the  function to be called at the appropriate location within the JavaScript file. 

The *`s_doPlugins`* function is called each time any of the following occurs:

* The *`t()`* function is called 
* The *`tl()`* function is called 
* An exit or download link is clicked 
* Any page element being tracked by visitor click map is clicked

The *`doPlugins`* function is used to run customized routines to gather or alter data. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

## Syntax and Possible Values {#section_5CFB94598521455E80947964A306EA89}

The *`s_doPlugins`* function should not be in quotes, and *`doPlugins`* should always be assigned to the exact name of the *`s_doPlugins`* function (if that function is renamed).

```js
s.doPlugins=s_doPlugins;
```

## Examples {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

## Configuration Settings {#section_641F0EC55E3349E5A3F8671446797074}

None

## Pitfalls, Questions, and Tips {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* The only reason to change the object name (such as from s to s_mc) is if you share content with or pull content from other customers. Renaming the *`s_doPlugins`* function to [!UICONTROL s_mc_doPlugins] ensures that another client's JavaScript file does not overwrite your *`doPlugins`* function. 

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. While the best solution is to use a different object name than other JavaScript files on the same page, doing so is not required.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

<!-- 

trackDownloadLinks.xml

 -->

Set  to 'true' if you would like to track links to downloadable files on your site. 

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | True  |

The *`trackDownloadLinks`* variable should only be set to 'false' if there are no links to downloadable files on your site, or you don't care to track the number of clicks on downloadable files. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. The data that is sent with a download link includes the link download URL, and visitor click map data for that link. If *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

## Syntax and Possible Values {#section_828492CC2A144BC68D18C30CF397EEFC}

The *`trackDownloadLinks`* variable is expected to be either 'true' or 'false.'

## Examples {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```js
s.trackDownloadLinks=true 

```

```js
s.trackDownloadLinks=false
```

## Configuration Settings {#section_9A5F69966BAF433A8DA2BCF655A652D1}

None

## Pitfalls, Questions, and Tips {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map. 
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 

trackExternalLinks.xml

 -->

If  is 'true,'  and  are used to determine whether any link clicked is an exit link.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | True  |

The *`trackExternalLinks`* variable should only be set to 'false' if there are no exit links on your site, or if you don't care to track the number of clicks on those exit links. An exit link is any link that takes a visitor off of your site. If *`trackExternalLinks`* is 'true,' then when you click an exit link, tracking data is immediately sent. The data that is sent with an exit link includes the link URL, link name, and visitor click map data for that link. If *`trackExternalLinks`* is 'false,' then visitor click map data for exit links on your site is likely to be under reported.

## Syntax and Possible Values {#section_267748949A7544658E1D838AAEF964B2}

The *`trackExternalLinks`* variable is expected to be either 'true' or 'false.'

```js
s.trackExternalLinks=true|false
```

## Examples {#section_EF18DB05884240F5B5062631E68E10A7}

```js
s.trackExternalLinks=true 

```

```js
s.trackExternalLinks=false
```

## Configuration Settings {#section_C8748CFE36324FAFB14C23E3E1FB5082}

None

## Pitfalls, Questions, and Tips {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map. 
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 

trackInlineStats.xml

 -->

The  variable determines whether ClickMap data is gathered. 

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | ClickMap  | False  |

## Syntax and Possible Values {#section_46B2C1DD0D104A01A9C239929420CD90}

```js
s.trackInlineStats=true|false
```

The *`trackInlineStats`* variable is expected to be either 'true' or 'false.'

## Examples {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Configuration Settings {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

None 

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

<!-- 

linkDownloadFileTypes.xml

 -->

The  variable is a comma-separated list of file extensions. 

If your site contains links to files with any of these extensions, the URLs of these links will appear in the [!UICONTROL File Downloads] report. 

<table id="table_03F3B33A50D3477583B5AC09DC864A2E"> 
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
   <td> N/A </td> 
   <td> N/A </td> 
   <td> Traffic &gt; Site Traffic &gt; File Downloads </td> 
   <td> <p>"exe,zip,wav,mp3,mov,mpg,avi,wmv, doc,pdf,xls" </p> </td> 
  </tr> 
 </tbody> 
</table>

The *`linkDownloadFileTypes`* variable is only relevant when *`trackDownloadLinks`* is set to 'True.'

Only left-mouse-clicks on a link are counted in the [!UICONTROL File Downloads] report. All file downloads that start automatically when a page loads, or that are only downloaded after a redirect, are not counted in the [!UICONTROL File Downloads] report. When you right-click a file and select the "Save Target As..." option, it is not counted in the [!UICONTROL File Downloads] report.

The *`linkDownloadFileTypes`* variable may be used to track clicks to RSS feeds. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

## Syntax and Possible Values {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Only include file extensions (no spaces).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Any file extension may be included in the list. Be careful not to include a common file extension, such as htm or aspx, in *`linkDownloadFileTypes`*. Doing so causes an extra image request to be sent for each click, which will be billed as a primary server call.

## Examples {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Configuration Settings {#section_CE24D5852E4D441A958A4EDDB82382A7}

None

## Pitfalls, Questions, and Tips {#section_786CF22D5553429EB6524B13774793BC}

* Only left-clicks on download files cause the URL to appear in the [!UICONTROL File Downloads] report. 
* Including a common file extension in *`linkDownloadFileTypes`* may significantly increase the total server calls sent to Adobe's servers. 
* Links to server-side redirects or HTML pages that automatically begin downloading a file are not counted unless the file extension is in *`linkDownloadFileTypes`*. 
* Links that use JavaScript (such as javascript:openLink( )) are not counted in file downloads.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

<!-- 

linkInternalFilters.xml

 -->

The  variable is used to determine which links on your site are exit links. 

It is a comma-separated list of filters that represent the links that are part of the site. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Paths > Entries & Exits > Exit Links  |  |

>[!NOTE]
>
>We had previously suggested setting the linkInternalFilters to javascript:. However, this resulted in all domains being considered external, including the current domain on which the tag resides. If you want several domains to be considered internal, you can add those, as shown in the examples below.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. Whether the target window of an exit link is a pop-up, or the existing window, does not affect whether the link appears in the exit links report. Exit links are only tracked if *`trackExternalLinks`* is set to `"true"`. (See [Link Tracking](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) in the Dynamic Tag management documentation for information about how DTM handles exit links.) The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). The filters are always applied to the absolute path of the URL, even if a relative path is used as the href value.

Be careful that all the domains of your site (and any partners who are using your JavaScript file) are included in *`linkInternalFilters`*. If you do not have all domains included in the list, all links on and to those domains are considered exit links, increasing the server calls sent. If you would like multiple domains or companies to use a single AppMeasurement for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. If you have vanity domains that immediately redirect to your main domain, those vanity domains do not need to be included in the list.

The following example illustrates how this variable is used. In this example, the URL of the page is [!DNL http://www.mysite.com/index.html].

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="http://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="http://www2.site3.com">Exit Link</a> 
<a href="http://www2.site1.com/partners/">Exit Link</a> 

```

## Syntax and Possible Values {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. No spaces are allowed.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

## Examples {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

## Configuration Settings {#section_546AC1FACB664ABFBCF312990097C987}

None

## Pitfalls, Questions, and Tips {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the AppMeasurement for JavaScript file may be served under in the filter list. 
* Periodically check the [!UICONTROL Paths] > [!UICONTROL Entries & Exits] > [!UICONTROL Exit] Links report to make sure that none of the entries in that report are incorrect. 

* Periodically review partner contracts to determine if they contain restrictions on link tracking. For example, you might be prohibited from tracking links that appear in partner display ads. Filter partner links by adding their domain to *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

<!-- 

linkLeaveQueryString.xml

 -->

By default, query strings are excluded from all reports. 

For some exit links and download links, the important portion of the URL can be in the query string, as shown in the following sample URL.

```js
http://www.mycompany.com/download.asp?filename=myfile.exe
```

The download file name can be defined in the query string and, consequently, the query string is necessary to make the [!UICONTROL File Downloads] report more accurate.

The *`linkLeaveQueryString`* variable determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports. 

<table id="table_323F7B871F514612950D129CD4AED697"> 
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
   <td> N/A </td> 
   <td> N/A </td> 
   <td> Exit Links <p>File Downloads </p> </td> 
   <td> false </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Setting *`linkLeaveQueryString`*=true includes all query string parameters for all exit links and download links.

## Syntax {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

## Examples {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

## Possible Values {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Configuring the Variable {#section_835FD74D3CA9425A9D091CACF88A6F1F}

No configuration is necessary for this variable.

## Pitfalls, Questions, and Tips {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting *`s.linkLeaveQueryString`*=true includes all query string parameters for all exit links and download links. 
* The *`linkLeaveQueryString`* variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

<!-- 

linkTrackVars.xml

 -->

The  variable is a comma-separated list of variables that are sent with custom, exit, and download links. 

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Any  | "None"  |

When populating *`linkTrackVars`*, do not use the 's.' prefix for variables. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="http://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 

```

Because the link to google.com is an exit link (unless you are Google), event1 and eVar1 are sent with the exit link data, increasing the instances associated with eVar1 and the number of times event1 is fired. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

## Syntax and Possible Values {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' instead of 's.eVar1.'

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

The *`linkTrackVars`* variable may contain only variables that are sent to [!DNL Analytics], namely: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`*, *`zip`*, and *`pageType`*.

## Examples {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

## Configuration Settings {#section_E387604B8A434A7F89A82A886649A89D}

None

## Pitfalls, Questions, and Tips {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls. 
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked. 
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events." 

* Do not use the "s." or "s_objectname." prefix for variables.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 

linkTrackEvents.xml

 -->

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link. 

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 

```

In the first link to [!DNL help.php], notice that the events variable retains the value that was set before the link was clicked,. This allows event1 to be sent with the custom link. In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if *`linkTrackVars`* contains "events." 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Conversion  | "None"  |

## Syntax and Possible Values {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

The *`linkTrackEvents`* variable is a comma-separated list of events (no spaces).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Only event names are allowed in *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). If a space appears before or after the event name, the event can not be sent with any link image requests.

## Examples {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

## Configuration Settings {#section_D938A47346D94A0C9E98FB327F2EF349}

None

## Pitfalls, Questions, and Tips {#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined. 

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function). 

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 

linkExternalFilters.xml

 -->

If your site contains many links to external sites, and you do not want to track all exit links, use  to report on a specific subset of exit links.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | Paths > Entries & Exits > Exit Links  | ""  |

The *`linkExternalFilters`* variable is an optional variable used in conjunction with *`linkInternalFilters`* to determine whether a link is an exit link. An exit link is defined as any link that takes a visitor away from your site. Whether the target window of an exit link is a popup or the existing window, it does not affect whether the link appears in the exit links report. Exit links are tracked only if *`trackExternalLinks`* is set to 'true.' The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). These filters are always applied to the absolute path of the URL, even if a relative path is used as the href value.

Most companies find that *`linkInternalFilters`* gives them enough control over exit links that they don't need *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

The following example illustrates how this variable is used. In this example, the URL of the page is [!DNL http://www.mysite.com/index.html].

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="http://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="http://www2.site3.com">Not an Exit Link</a> 
<a href="http://www.site1.com">Exit Link</a> 
<a href="http://www2.site3.com/partners/offer.asp">Exit Link</a> 

```

## Syntax and Possible Values {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. No spaces are allowed.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Any portion of a URL might be included in *`linkExternalFilters`*, separated by commas.

## Examples {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

## Configuration Settings {#section_2D0CA911855B4B3698145FC18D5021C3}

None

## Pitfalls, Questions, and Tips {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links. 

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`. 

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 

s_usePlugins.xml

 -->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.' 

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request. 

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | True  |

## Syntax and Possible Values {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

The [!UICONTROL usePlugins] variable is expected to be either 'true' or 'false.'

## Examples {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

## Configuration Settings {#section_DFD41717134147E988B6AFC7DE5BB9E3}

None 
