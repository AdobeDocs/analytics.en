---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.account

The  variable determines the report suite where data is stored and reported.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. The report suite ID is determined by Adobe.

## Parameters

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|40 Bytes|In the URL path|N/A|N/A|

Each report suite ID must match the value created in the [!DNL Admin Console]. Each report suite ID must be 40 bytes or less, but the aggregate of all report suites (the entire comma-separated list) has no limit.

The report suite is the most fundamental level of segmentation in reporting. You can set as many report suites as your contract allows. Each report suite refers to a dedicated set of tables that are populated in Adobe's collection servers. A report suite is identified by the `s_account` variable in your JavaScript code.

Within [!DNL Analytics], the site drop-down box in the upper left of the reports displays the current report suite. Each report suite has a unique identifier called a report suite ID. The `s_account` variable contains one or more report suite IDs to which data is sent. The report suite ID value, which is invisible to [!DNL Analytics] users, must be provided or approved by Adobe before you use it. Every report suite ID has an associated "friendly name" that can be changed in the report suites section of the [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. The value in the path is the only value that determines the destination report suite. The bold text below shows the report suites that data is sent to, as it appears in the debugger. See [DigitalPulse Debugger](/help/implement/impl-testing/debugger.md).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Syntax and Possible Values

The report suite ID is an alphanumeric string of ASCII characters, no more than 40 bytes in length. The only non-alphanumeric character allowed is a hyphen. Spaces, periods, commas and other punctuation are not allowed. The `s_account` variable may contain multiple report suites, all of which receive data from that page.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

## Examples

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configuring the Variable in Analytics

The friendly name associated with each report suite ID can be changed by Adobe [!DNL Customer Care]. The friendly name can be seen in [!DNL Analytics] in the site drop-down box in the top, left section of the screen.

## Pitfalls, Questions, and Tips

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Use the [!DNL DigitalPulse Debugger] to determine the destination report suite(s).

* In some cases, [!DNL VISTA] can be used to alter the destination report suite. Using [!DNL VISTA] to re-route or copy the data to another report suite is recommended when using first-party cookies, or if your site has more than 20 active report suites.

* Always declare `s_account` inside the JS file or just before it is included.
