---
description: Publishing lists provide an easy way to send various reports specific to different groups of your organization without creating several separate scheduled reports. Publishing lists are useful if you have location-specific report suites and would like to provide each respective department a copy of a specific dashboard. Alternatively, you can use publishing lists to send data to many people without having to separately type in their email addresses, if you work with a single report suite.
title: Publishing Lists
feature: Admin Tools
uuid: 07dad661-c302-4981-80d1-3169ad1fe90e
exl-id: 5c9a0ae7-742b-4247-bcbc-2e979af6160c
---
# Publishing Lists

Publishing lists provide an easy way to send various reports specific to different groups of your organization without creating several separate scheduled reports. Publishing lists are useful if you have location-specific report suites and would like to provide each respective department a copy of a specific dashboard. Alternatively, you can use publishing lists to send data to many people without having to separately type in their email addresses, if you work with a single report suite.

Multiple publishing lists can be specified when scheduling a report.

## End-of-life of Publishing Lists

As you are probably aware, Adobe will deprecate Reports and Analytics (R&A) as well as the Site Catalyst point product on Dec 31, 2023. [You can learn more about the end-of-life and how you can prepare for it here](https://express.adobe.com/page/6WnF8JK6IRDhf/).
 
One of the features in R&A that is slated to reach end-of-life on this date is Publishing Lists. Some features like Calendar Events and Page Summary Report do/will have a parity version in Analysis Workspace. However, Publishing Lists is not one of them and will be deprecated when R&A reaches its end of life. You will not be able to create new or access existing Publishing Lists to send or schedule Analysis Workspace projects.
 
To mitigate any disruption to your current report-distribution workflows that rely on Publishing Lists, we request that you consider the following alternatives:
 
* If you use Publishing Lists to distribute the same version of the report to multiple users (without applying report suite overrides):
 
   Once you recreate your reports in Analysis Workspace as projects, you can use a combination of a contact group or distribution list created for your mail client and Workspace's Scheduled Projects feature to send or schedule the recurring delivery of the project; like Publishing Lists, a PDF/CSV version of the project is then sent to every email ID that is part of the group/list. You can learn more about the Scheduled Projects feature here.
 
* If you use Publishing Lists to distribute multiple versions of the report or dashboard to multiple users (via the report suite override feature):
 
   Analysis Workspace does not support report-suite overrides or, unlike R&A reportlets and dashboards, the ability to lock report suites when sharing or scheduling projects. To replicate the workflow, you may have to create multiple versions of the same project with a different report suite applied to each version, and then use the scheduled project feature described above.
 
For additional questions or support, please reach out to Adobe Customer Care.

## Publishing List Manager Descriptions {#section_099DF8AC5691495F9B22C71266DD6004}

| Element | Description |
|--- |--- |
|[!UICONTROL Search for]|Lets you filter the table to search for a publishing list.|
|[!UICONTROL Report Suites to Include]|Overrides the report suite for a scheduled report or all reportlets in a dashboard. Though there is no technical limit on the number of separate report suite entries, it is recommended to limit it to approximately 50. There is no established limit on the number of emails that can be included.|
|[!UICONTROL E-mail Addresses]|A comma-delimited list of all emails that will receive the report with the new report suite.  Click **[!UICONTROL Click to Edit]** to specify the Email addresses to receive. Enter each Email address, separating multiple Email addresses with a semi-colon (;). Press `<Enter>` when finished entering Email addresses. <br>The Email Count field displays the number of Email addresses currently associated with the report suite entry.|
|[!UICONTROL Duplicate]|Creates a copy of the publishing list.|
