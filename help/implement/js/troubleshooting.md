---
title: Troubleshoot JavaScript implementation
description: Learn about common issues and best practices for troubleshooting your JavaScript implementation.
feature: Implementation Basics
exl-id: e7181e78-65bf-446d-8d5c-b47323dbec1d
role: Developer
TQID: https://experienceleague.adobe.com/U97L94cxnWYpnqsJ3FJh7EBbdIHpFHxfJP7uqoqrGgU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
---
# Troubleshoot JavaScript implementation

The following are several reasons why your organization might have issues with correctly getting data into Adobe Analytics.

## Using quotes

Most variables sent to Adobe are strings. In JavaScript, you can use either single quotes or double quotes.

### Mixing quotes to define a variable

As a best practice, make sure that you are consistent with the types of quotes you use. If a single quote designates the start of a string, a single quote must be used to close it.

For example, both `s.eVar1 = 'Value'` and `s.eVar1 = "Value"` are both valid. `s.eVar1 = 'Value"` is not valid.

### Including single or double quotes in a string

Sometimes including a single or double quote in a string is desired. For example, you want to include the value `Alex's sale` or `John the "Hunter"` in reports. There are two methods to include these values:

* **Use the other quote type**: For example, `s.eVar1 = "Alex's sale"` and `s.eVar1 = 'John the "Hunter"'` are both valid.
* **Escape quotation marks**: Use a backslash to escape quotation marks. For example, `s.eVar1 = 'Alex\'s sale'` and `s.eVar1 = "John the \"Hunter\""` are both valid.

### Avoid using curly quotes

Some programs automatically convert neutral quotes (`"..."` and `'...'`) into curly quotes (`"..."` and `'...'`). Avoid using document editors (such as Microsoft Word), or transmitting code snippets through email. Curly quotes cannot be used in JavaScript.

## Reference the Analytics object

All variables sent to Adobe use the Analytics object. Most implementations use the `s` object. Make sure that when referencing variables that you include the Analytics object in your reference.

For example, `s.eVar1 = 'Value'` is valid, while `eVar1 = 'Value'` is not.

## Define each variable once

When a track function (`s.t()`) runs, AppMeasurement takes all defined variables and compiles them into an image request. If you define a variable more than once in your implementation, only the latest value is used. Make sure that all variable values contain the correct value when the track function runs.

## Correct variable capitalization

Some variables use uppercase letters. JavaScript variables are case-sensitive. Make sure that you use the correct case when defining variables. For example, `s.eVar1 = 'Value'` is valid, while `s.evar1 = 'Value'` is not.

## Plug-ins

Some organizations use plug-ins to improve their implementation of Adobe Analytics. When upgrading AppMeasurement versions, do not forget to re-include any installed plug-ins. The code created in the [!UICONTROL Code Manager] does not have any plug-in code with it. Make a copy of your existing code in case you need to revert to a previous version of AppMeasurement.

## White space in variable values

In HTML there are several characters that create whitespace. These include a space, a tab, and a carriage return (or linefeed). Consider the following example:

```html
<head>
  <title>
    Home Page
  </title>
</head>
<body>
<script language="javascript">
  s.pageName = document.title;
</script>
</body>
```

In this case, `document.title` populates `s.pageName`, which receives a value of "Home Page". However, some browsers can interpret white space differently. The result can be either of two following examples:

```js
s.pageName = "Home Page";
```

```js
s.pageName = "        Home Page";
```

These two variable values are considered separate in Adobe Analytics. However, the white space is automatically removed for display purposes. The result is a report that displays two seemingly identical "Home Page" line items. Make sure that variable values do not contain whitespace before or after the desired value.

## Truncated image requests

Implementations that populate many variables with long values can sometimes run into truncated image requests. Some older browsers, such as Internet Explorer, impose a 2083-character limit on image request URLs. If your organization faces very long image requests, try the following:

* **Use the Experience Cloud ID service**: AppMeasurement libraries 1.4.1 and later automatically send image requests using HTTP POST if they are too long. Data sent using this method is not truncated regardless of length. See [Adobe Experience Cloud ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html) for more information.
* **Use processing rules**: [Processing rules](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) can copy values from one variable to another. This method saves you from setting the same value in multiple variables. For example:

  Always execute:<br>
  Overwrite value of prop1 with eVar1<br>
  Overwrite value of eVar2 with eVar1<br>
  Overwrite value of prop2 with eVar1<br>

  Then set eVar1 in your implementation:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  ```

* **Use dynamic variables**: If your implementation populates many variables with the same value, you can use [dynamic variables](/help/implement/vars/page-vars/dynamic-variables.md) to shorten the request URL:

  ```js
  s.eVar1 = "The quick brown fox jumps over the lazy dog";
  s.eVar2 = "D=v1";
  s.prop1 = "D=v1";
  s.prop2 = "D=v1";
  ```

* **Use classifications**: If product or page names are unusually long, you can use an identifying value or code, then use [classifications](/help/components/classifications/classifications-overview.md) to display a more friendly name.
