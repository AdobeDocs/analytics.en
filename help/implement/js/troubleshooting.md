---
title: Troubleshoot JavaScript implementation
description: Learn about common issues and best practices for troubleshooting your JavaScript implementation.
---

# Troubleshoot JavaScript implementation

The following are several reasons why your organization might have issues with correctly getting data into Adobe Analytics.

## Using quotes

Most variables sent to Adobe are strings. In JavaScript, you can use either single quotes or double quotes.

### Mixing quotes to define a variable

As a best practice, make sure you are consistent with the types of quotes you use. If a single quote designates the start of a string, a single quote must be used to close it.

For example, both `s.eVar1 = 'Value'` and `s.eVar1 = "Value"` are both valid. `s.eVar1 = 'Value"` is not valid.

### Including single or double quotes in a string

Sometimes including a single or double quote in a string is desired. For example, you want to include the value `Alex's sale` or `John the "Hunter"` in reports. There are two methods to include these values:

* **Use the other quote type**: For example, `s.eVar1 = "Alex's sale"` and `s.eVar1 = 'John the "Hunter"'` are both valid.
* **Escape quotation marks**: Use a backslash to escape quotation marks. For example, `s.eVar1 = 'Alex\'s sale'` and `s.eVar1 = "John the \"Hunter\""` are both valid.

### Avoid using curly quotes

Some programs automatically convert neutral quotes (`"..."` and `'...'`) into curly quotes (`“...”` and `‘...’`). Avoid using document editors (such as Microsoft Word), or transmitting code snippets through email. Curly quotes cannot be used in JavaScript.

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
