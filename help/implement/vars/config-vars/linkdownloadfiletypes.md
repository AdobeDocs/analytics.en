---
title: linkDownloadFileTypes
description: Determine file extensions that automatically get tracked as download links.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
---
# linkDownloadFileTypes

When [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) or [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) is enabled and a visitor clicks on a link, AppMeasurement checks the URL of the link for filetype extensions. If the link URL contains a matching filetype, a download link image request is automatically sent.

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
>For these download types, you can manually send a [`link tracking`](../functions/tl-method.md) call.

If a clicked link matches both exit link and download link criteria, the download link type takes priority.

## Download link qualifier using the Web SDK extension

The [!UICONTROL Download link qualifier] text field uses regex to determine if a clicked link qualifies to be a download link.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under [!UICONTROL Adobe Experience Platform Web SDK].
1. Under [!UICONTROL Data Collection], set the desired value in the **[!UICONTROL Download link qualifier]** text field.

## Download link qualifier manually implementing the Web SDK

[Configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) the SDK using [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). The field uses regex on the clicked URL to determine if it is a valid download link. If `downloadLinkQualifier` is not defined, the default value is set to `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Download Extensions using the Adobe Analytics extension

Download Extensions is a list of file extensions with a field to add more under the [!UICONTROL Link Tracking] accordion when configuring the Adobe Analytics extension.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the desired tag property.
3. Go to the [!UICONTROL Extensions] tab, then click the **[!UICONTROL Configure]** button under Adobe Analytics.
4. Expand the [!UICONTROL Link Tracking] accordion, which reveals the **[!UICONTROL Download Extensions]** field.

Add file extensions to the list by entering text in the field and clicking **[!UICONTROL Add]**. Remove file extensions from the list by clicking their respective **'X'** icon.

## s.linkDownloadFileTypes in AppMeasurement and the Analytics extension custom code editor

The `s.linkDownloadFileTypes` variable is a string of comma-separated file extensions. Do not use spaces.

If this variable is not defined, automatic download link tracking does not work (even if [`trackDownloadLinks`](trackdownloadlinks.md) is `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
