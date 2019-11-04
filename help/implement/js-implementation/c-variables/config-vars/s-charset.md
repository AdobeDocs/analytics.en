---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.charSet

The charSet property, which is normally set in the JavaScript file, is used by Analytics to convert incoming data into UTF-8 for storage and reporting by Analytics.

>[!Note:] The charSet property is required when sending data to a multi-byte report suite and should never be used with a standard report suite. Setting the charSet property with a standard ISO report suite can result in variable truncation or unexpected character conversion.

The value of the charSet property should match the web page encoding in the META tag or http header, even though the syntax may differ slightly. Although the META tag may use an alias for the encoding, the value of charSet should use the preferred (or official) name of the encoding.

Some of the more common encodings with their preferred name and aliases are listed in the following table.

|Preferred Name|Aliases|
|--- |--- |
|ISO-8859-1|ISO_8859-1, CP819, latin1|
|ISO-8859-2 |ISO_8859-2, latin2 |
|ISO-8859-5|ISO_8859-5, cyrillic|
|Big5|Big-5|
|Shift_JIS|SJIS|

Because numerous encodings and aliases exist, contact your Implementation Consultant or Adobe Customer Care to confirm the proper value for charSet if it does not appear in the table above.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Any non-blank value of the charSet parameter will cause data to be converted into UTF-8 for storage. Any characters in the 128-255 range will be converted to the proper UTF-8 two-byte sequence and stored. These characters will not display properly in a standard report suite. Therefore, the charSet property should never be used with a standard report suite.

Likewise, a blank value of the charSet parameter will bypass the data conversion process, and any characters in the range 128-255 will be stored as a single byte. These characters will not display properly in a multi-byte report suite since the single-byte codes for these characters are not valid UTF-8. Therefore, the charSet parameter should always be used with a multi-byte report suite. Additionally, the proper value should be used with respect to the web page encoding. 

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

## Parameters

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|N/A|CE|N/A|""|

## Syntax and Possible Values

```js
s.charSet="character_set"
```

## Examples

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```
