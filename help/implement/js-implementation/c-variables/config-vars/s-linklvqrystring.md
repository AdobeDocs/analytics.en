---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
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

*Note: Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.*

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

## Automatic Tracking of Exit Links and File Downloads

The JavaScript file can be configured to automatically track file downloads and exit links based on parameters that define file download file types and exit links.

The parameters that control automatic tracking are as follows:

```
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 

```

The parameters `trackDownloadLinks` and `trackExternalLinks` determine if automatic file download and exit link tracking are enabled. When enabled, any link with a file type matching one of the values in `linkDownloadFileTypes` is automatically tracked as a file download. Any link with a URL that does not contain one of the values in `linkInternalFilters` is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

### Example 1

The file types `.jpg` and `.aspx` are not included in `linkDownloadFileTypes` above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter `linkLeaveQueryString` modifies the logic used to determine exit links. When `linkLeaveQueryString`=false, exit links are determined using only the domain, path, and file portion of the link URL. When `linkLeaveQueryString`=true, the query string portion of the link URL is also used to determine an exit link.

### Example 2 

With the following settings, the example below will be counted as an exit link:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 

```

### Example 3

With the following settings, the link below is not counted as an exit link:

```
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 

```

*Note: A single link can be tracked only as a file download or exit link, with file download taking priority. If a link is both an exit link and file download based on the parameters `linkDownloadFileTypes` and `linkInternalFilters`, it is tracked and reported as a file download and not an exit link.*