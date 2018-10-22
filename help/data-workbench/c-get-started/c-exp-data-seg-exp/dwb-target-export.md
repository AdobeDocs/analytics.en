---
description: Export Data Workbench data to Adobe Target using TargetBulkUpload.exe from the Detail Table.
seo-description: Export Data Workbench data to Adobe Target using TargetBulkUpload.exe from the Detail Table.
seo-title: Export to Adobe Target
title: Export to Adobe Target
uuid: 45ec764a-01d1-440c-b07c-e3611289542e
index: y
internal: n
snippet: y
---

# Export to Adobe Target

Export Data Workbench data to Adobe Target using TargetBulkUpload.exe from the Detail Table.

Data Workbench lets you export files to integrate with Adobe Target as part of an integrated Adobe Experience Cloud.

The **[!DNL TargetBulkUpload]** file is found in the *Server\Scripts* folder in the server installation files. The executable has retry logic, as well as additional logic to optimize performance.

You can modify the `TargetBulkUpload.cfg` file and move it to *Server/Admin/Export* folder before running the upload script. For example, you can set a Max Timeout Interval to 720 minutes (default) to timeout the upload after the specified period.

**How it works**

After the data gets successfully sent to Target, the status of the upload is continuously monitored. If the upload succeeds, a success message is logged. If the upload fails or is pending, the monitoring continues. You can configure the timeout interval in the `TargetBulkUpload.cfg` file. If the upload gets stuck at Target, a message is logged and the status can still be monitored.

There are two log files generated in the trace for the triggered export under [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log` 
* `targetbulkuploadexportname.log.completed`

The `targetbulkuploadexportname.log` file has the detailed status for all the records of multiple batches, the edge server they are going to, and the status (successful, failed, profile not found, status unknown, and stuck). In case any batch is found to be stuck, the batch is not processed any further. A stuck batch URL is available to track the status. See the following example data from the `targetbulkuploadexportname.log.completed` file:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

The stuck status value is incremented with the total stuck batch size regardless of how many uploads are successful or failed. The total rows value is also incremented by the same number of stuck batch size.

>[!NOTE]
>
>Previously, DWB data was exported using the [!DNL ExportIntegration.exe]. Currently only the MMP, CRS, and S/FTP exports are used with this executable. Adobe Target integration now uses the [!DNL TargetBulkUpload.exe] in Data Workbench.

