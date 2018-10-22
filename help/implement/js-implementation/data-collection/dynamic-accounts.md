---
description: The .js file can be configured to automatically select a report suite ID. The .js file automatically sends the image request to the report suite based on the URL. For example, if the URL is www.mysite.com, the image request is automatically sent to report suite A. If the URL is www.mysite1.com, the image request is automatically sent to report suite B.
keywords: Analytics Implementation
seo-description: The .js file can be configured to automatically select a report suite ID. The .js file automatically sends the image request to the report suite based on the URL. For example, if the URL is www.mysite.com, the image request is automatically sent to report suite A. If the URL is www.mysite1.com, the image request is automatically sent to report suite B.
seo-title: Report suite IDs - dynamic accounts
solution: Analytics
title: Report suite IDs - dynamic accounts
topic: Developer and implementation
uuid: cbd18c84-1a1a-470f-a414-56cf50a51c9f
index: y
internal: n
snippet: y
---

# Report suite IDs - dynamic accounts

The .js file can be configured to automatically select a report suite ID. The .js file automatically sends the image request to the report suite based on the URL. For example, if the URL is www.mysite.com, the image request is automatically sent to report suite A. If the URL is www.mysite1.com, the image request is automatically sent to report suite B.

These strings can be found within any of the following:

* Host/domain (default setting) 
* Path 
* Query String 
* Host/domain and Path 
* Path and Query String 
* Full URL

For more information on configuring [!DNL Analytics] to automatically select a [!UICONTROL Report Suite ID], contact Adobe Live Support.

## Defining the URL Segment to Match {#section_8099162F75F641CFBE46FD814450EF36}

Given the following sample URL, the portions of the URL are shown below, along with the [!UICONTROL s.dynamicAccountMatch] variable that must be set. (The default - if [!UICONTROL s.dynamicAccountMatch] is not defined - is to search the Host/Domain Name only). 
Sample URL: http://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321 

|  Portion  | Example (from above)  |
|---|---|
|  Host/Domain Name  | www.client.com  |
|  Path  | directory1/directory2/filename.html  |
|  Query String  | param1=1234&param2=4321  |
|  Host/Domain and Path  | www.client.com/directory1/directory2/filename.html  |
|  Path and Query String  | directory1/directory2/filename.html?param1=1234&param2=4321  |
|  URL  | http://www.client.com/directory1/directory2/filename.html?param1=1234&param2=4321  |
|  Portion  | s.dynamicAccountmatch  |
|  Host/Domain Name  | Undefined  |
|  Path  | window.location.pathname  |
|  Query String  | (window.location.search?window.location.search:"?")  |
|  Host/Domain and Path  | window.location.host+window.location.pathname  |
|  Path and Query String  | window.location.pathname+(window.location.search?window.location.search:"?")  |
|  URL  | window.location.href  |

Consider the following example:

* s.dynamicAccountSelection=true 
* s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite2=clientdirectory;reportsuite1=client.com" 
* s.dynamicAccountMatch=window.location.host+window.location.pathname

## Multiple Rules {#section_163FED1C1FA74C48BCB78B0D67EF36AE}

If multiple rules are selected (see example above), the rules are executed from left to right. The rules stop as soon as a match is made, as shown below (with the given set of rules).

* s.dynamicAccountSelection=true 
* s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com"

The code first checks to determine if "qa.client.com" exists within the Host/Domain Name. If so, the report suite "devreportsuite1" is selected, and the match stops. Separate multiple rules with semi-colons.

## Default Report Suite {#section_0360D724929348B0B211708B5BA15647}

The *`s_account`* variable can be set first, and acts as a default value in case any of the specified strings cannot be found. Below is an example: 

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 

```

In the case above, if the host/domain name did not contain either "qa.client.com" or "client.com," the report suite "defaultreportsuiteid" would be used. 
