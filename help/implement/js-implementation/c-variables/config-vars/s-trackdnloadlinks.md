---
description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
keywords: Analytics Implementation
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: 
title: Dynamic variables
---

# s.trackDownLoadLinks

Set  to 'true' if you would like to track links to downloadable files on your site.

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  N/A  | N/A  | N/A  | True  |

The *`trackDownloadLinks`* variable should only be set to 'false' if there are no links to downloadable files on your site, or you don't care to track the number of clicks on downloadable files. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. The data that is sent with a download link includes the link download URL, and visitor click map data for that link. If *`trackDownloadLinks`* is 'false,' then visitor click map data for links to downloadable files on your site is likely to be under reported.

## Syntax and Possible Values

The *`trackDownloadLinks`* variable is expected to be either 'true' or 'false.'

## Examples

```
js
s.trackDownloadLinks=true 

```

```
js
s.trackDownloadLinks=false
```

## Configuration Settings

None

## Pitfalls, Questions, and Tips

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.

* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

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