---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# visitorNamespace

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
