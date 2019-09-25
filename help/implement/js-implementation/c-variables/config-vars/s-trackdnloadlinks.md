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