---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.linkLeaveQueryString

By default, query strings are excluded from all reports. 

For some exit links and download links, the important portion of the URL can be in the query string, as shown in the following sample URL.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

The download file name can be defined in the query string and, consequently, the query string is necessary to make the [!UICONTROL File Downloads] report more accurate.

The *`linkLeaveQueryString`* variable determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports. 

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|N/A|N/A|Exit Links File Downloads|false|

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

## Syntax

```js
s.linkLeaveQueryString=[false/true]
```

## Examples

```js
s.linkLeaveQueryString=false
```

## Possible Values

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

## Configuration Settings

No configuration is necessary for this variable.

## Pitfalls, Questions, and Tips

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links. 
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.
