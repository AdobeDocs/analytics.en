---
description: File Downloads helps you understand how often your visitors download files from your site. Examples of file downloads may be word processor documents, spreadsheets, audio files, movie files, user manuals, and so on. This includes both files being saved and opened directly from the browser, as well as files saved to the user's computer. The report shows the name of the file being downloaded, including the complete URL required to access the file.
title: File Downloads
topic: Reports
uuid: 897fc221-aa30-4eac-aca6-bccb76adaf71
---

# File Downloads

File Downloads helps you understand how often your visitors download files from your site. Examples of file downloads may be word processor documents, spreadsheets, audio files, movie files, user manuals, and so on. This includes both files being saved and opened directly from the browser, as well as files saved to the user's computer. The report shows the name of the file being downloaded, including the complete URL required to access the file.

 **Navigation**

**[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Links]** > **[!UICONTROL File Downloads]**

If this report is not available in the default location, please check with your administrators, who may have changed the default menu structure to better serve your organization's unique needs.

Use this report to:

* Determine the files that are downloaded most frequently from your site.
* Understand if certain files are downloaded more often during specific time periods.
* Validate that all formats for a given document are required.

  For example, perhaps you are currently translating your user manuals into twelve languages and making them available via your Web site. With file download reporting, you can know how often each user manual version is downloaded and can assess the value of continuing to translate the user manual into all twelve languages.

**Troubleshooting**

Marketing reports capture information on files downloaded from any page of your site that contains JavaScript code. However, certain variables must be present and set correctly so that file download information can be reported. If this report is not displaying data, or does not show the expected values, follow the steps below to validate your implementation.

1. On your site, locate the global JavaScript file. This is frequently named [!DNL s_code.js], but may have been renamed. If it has been renamed, you can search the JavaScript files on your site for the value *`s.account`*, which is a part of the JavaScript code.

1. In the file, locate the [s.trackDownloadLinks](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/trackdownloadlinks.html) variable. Ensure that it is set to *true* 

1. Locate the [s.linkDownloadFileTypes](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/linkdownloadfiletypes.html) variable. Ensure that all of the desired file extensions are present in this list. If necessary, add missing extensions like [!DNL .zip], [!DNL .pdf], and so on.)

If these variables appear to be configured correctly, but the [!UICONTROL File Downloads Report] still is not receiving data, your organization's supported users should contact Customer Care.
