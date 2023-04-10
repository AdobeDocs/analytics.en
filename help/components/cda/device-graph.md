---
title: Device graph
description: Understand the prerequisites and limitations of stitching data using the device graph.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
---
# Device graph

Cross-Device Analytics can use the Private Graph to stitch data together. The Private Graph is a repository of hashed device ID's that is specific to your organization. CDA regularly communicates with the device graph to link devices together.

## Prerequisites specific to the device graph

If you intend to implement Cross-Device Analytics using the device graph method, the following are required. Work with teams within your organization and your Adobe Account Team to ensure that you meet all of the following.

>[!WARNING]
>
>Failure to meet all prerequisites can result in the inability to enable Cross-Device Analytics or poor results when stitching data.

* All prerequisites listed on the [overview page](overview.md).
* Your organization must use the [Adobe Experience Platform Identity Service Private Graph](https://business.adobe.com/products/experience-platform/identity-service.html). See also the [Home Page](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html) in the Identity Service user guide.
* Your implementation must use the latest version of the Experience Cloud ID Service (ECID). See the [Home Page](https://experienceleague.adobe.com/docs/id-service/using/home.html) in the ID Service user guide. Most implementations using [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) in Adobe Experience Platform likely already have ID Service deployed.
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. See [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) in the ID Service user guide.

## Limitations specific to the device graph

* Legacy Analytics ID's are not supported. Only visitors with Experience Cloud ID's are stitched.
* If your organization uses a Private Graph, new devices take up to 24 hours to be stitched. 
* 3rd-party device graphs are not supported.

## Next steps

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).
