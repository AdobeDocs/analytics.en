---
description: null
seo-description: null
seo-title: PHP
solution: Analytics
subtopic: Release notes
title: PHP
topic: Developer and implementation
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
index: y
internal: n
snippet: y
---

# PHP{#php}

>[!NOTE]
>
>To find the current library version, turn on debug logging.

## 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Release Date: **August 2014**

* Internal changes to support upcoming functionality.

## 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Release Date: **July 2012**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. This caused non-secure pages to try to make a secure image request.

## 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

Measurement Library for PHP 1.1 includes the following updates from version 1.0:

* Better GeoSegmentation accuracy (when `sendFromServer` is enabled). 
* Fixed bug so user can now append to `userAgent` variable. 
* Image beacon is now more compliant with more mobile browsers. 
* The `imageDimensions` variable now defaults to 5x5 when mobile is enabled. 
* Refined bot detection list. 
* Added debug information (HTTP headers, response, errors, and so forth) when `debugTracking` and `sendFromServer` are enabled. 

* Added the `debugFilename` variable (when `sendFromServer` is enabled). 

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set. 

* Full support for CGI implementations of PHP. 
* Performance enhancements.

