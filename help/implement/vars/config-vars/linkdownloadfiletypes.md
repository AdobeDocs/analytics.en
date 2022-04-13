---
title: linkDownloadFileTypes
description: Determine file extensions that automatically get tracked as download links.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
---
# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. If the link URL contains a filetype found in `linkDownloadFileTypes`, a download link image request is automatically sent.

Use `linkDownloadFileTypes` to customize what file extensions you want to count as download links.

>[!NOTE]
>
>Only actual clicks are tracked automatically. The following types of links are not automatically tracked:
>
>* File downloads that start automatically when a page loads
>* Downloads that trigger after a redirect
>* Right-clicking and selecting 'Save Target As...'
>* Links that use JavaScript, such as `javascript:openLink()`
>
>For these download types, you can manually call the [`tl()`](../functions/tl-method.md) method.

If a clicked link matches both exit link and download link criteria, the download link type takes priority.

## Download Extensions using tags in Adobe Experience Platform

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired property.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the [!UICONTROL Download Extensions] field.

Add file extensions to the list by entering text in the field and clicking [!UICONTROL Add]. Remove file extensions from the list by clicking their respective 'X' icon.

## s.linkDownloadFileTypes in AppMeasurement and custom code editor

The `s.linkDownloadFileTypes` variable is a string of comma-separated file extensions. Do not use spaces.

If this variable is not defined, automatic download link tracking does not work (even if [`trackDownloadLinks`](trackdownloadlinks.md) is `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
