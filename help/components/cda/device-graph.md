---
title: Device graph
description: Understand the prerequisites and limitations of stitching data using the device graph.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
---
# Device graph

Cross-Device Analytics provides two distinct methods to stitch data together. This method uses the Adobe Experience Platform Identity Service Co-op Graph or Private Graph to stitch data together. CDA regularly communicates with the device graph to link devices together.

## Differences between co-op graph and private graph

Adobe offers two types of device graphs as part of the ID service:

* **Co-op graph**: A repository of hashed device ID's that any customer can contribute to and reference. Since this type of device graph is collaborative, it typically matches more devices than a private graph.
* **Private graph**: A repository of hashed device ID's that only your organization references.

## Prerequisites specific to the device graph

If you intend to implement Cross-Device Analytics using the device graph method, the following are required. Work with teams within your organization and your Adobe Account Manager to ensure that you meet all of the following.

>[!IMPORTANT]
>
>Failure to meet all prerequisites can result in the inability to enable Cross-Device Analytics or poor results when stitching data.

* All prerequisites listed on the [overview page](overview.md).
* Your organization must use the Adobe Experience Platform Identity Service Co-op Graph or Private Graph. See the [Home Page](https://experienceleague.adobe.com/docs/ device-co-op/using/home.html) in the Device Co-op user guide.
* Your implementation must use the latest version of the Experience Cloud ID Service. See the [Home Page](https://experienceleague.adobe.com/docs/ id-service/using/home.html) in the Experience Cloud Identity Service user guide. Most implementations using Adobe Experience Platform Launch likely already have ECID deployed.
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. See [`setCustomerIDs`](https://experienceleague.adobe.com/docs/ id-service/using/id-service-api/methods/setcustomerids.html) in the Experience Cloud Identity Service user guide.

## Limitations specific to the device graph

* Legacy Analytics ID's are not supported. Only visitors with Experience Cloud ID's are stitched.
* If your organization uses a Private Graph, new devices take up to 24 hours to be stitched. 
* If your organization uses the Co-op Graph, new devices visiting your site can take up to two weeks to be stitched. The level of stitching in CDA for the most recent two weeks is typically lower than for date ranges older than two weeks.
* 3rd-party device graphs are not supported.

## Next steps

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).
