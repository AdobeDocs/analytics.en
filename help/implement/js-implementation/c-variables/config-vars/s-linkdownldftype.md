---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
solution: 
title: Dynamic variables
---

# s.linkDownloadFileTypes

The  variable is a comma-separated list of file extensions.

If your site contains links to files with any of these extensions, the URLs of these links will appear in the [!UICONTROL File Downloads] report.

|Max Size|Debugger Parameter|Reports Populated|Default Value|
|--- |--- |--- |--- |
|N/A|N/A|Traffic > Site Traffic > File Downloads|"exe,zip,wav,mp3,mov,mpg,avi,wmv, doc,pdf,xls"|

The *`linkDownloadFileTypes`* variable is only relevant when *`trackDownloadLinks`* is set to 'True.'

Only left-mouse-clicks on a link are counted in the [!UICONTROL File Downloads] report. All file downloads that start automatically when a page loads, or that are only downloaded after a redirect, are not counted in the [!UICONTROL File Downloads] report. When you right-click a file and select the "Save Target As..." option, it is not counted in the [!UICONTROL File Downloads] report.

The *`linkDownloadFileTypes`* variable may be used to track clicks to RSS feeds. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

## Syntax and Possible Values

Only include file extensions (no spaces).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Any file extension may be included in the list. Be careful not to include a common file extension, such as htm or aspx, in *`linkDownloadFileTypes`*. Doing so causes an extra image request to be sent for each click, which will be billed as a primary server call.

## Examples

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

## Configuration Settings*

None

## Pitfalls, Questions, and Tips

* Only left-clicks on download files cause the URL to appear in the [!UICONTROL File Downloads] report.
* Including a common file extension in *`linkDownloadFileTypes`* may significantly increase the total server calls sent to Adobe's servers.
* Links to server-side redirects or HTML pages that automatically begin downloading a file are not counted unless the file extension is in *`linkDownloadFileTypes`*.
* Links that use JavaScript (such as javascript:openLink( )) are not counted in file downloads.

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