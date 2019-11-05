---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
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
