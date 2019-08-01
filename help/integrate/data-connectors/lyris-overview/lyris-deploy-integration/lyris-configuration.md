---
description: Steps describing what to configure within Lyris following the completion of the wizard.
seo-description: Steps describing what to configure within Lyris following the completion of the wizard.
seo-title: Configuration within the Lyris EmailLabs
solution: Analytics
title: Configuration within the Lyris EmailLabs
uuid: 1276176d-e5e9-451a-9a7b-9f29a340a25b
index: y
internal: n
snippet: y
---

# Configuration within the Lyris EmailLabs{#configuration-within-the-lyris-emaillabs}

Steps describing what to configure within Lyris following the completion of the wizard.

1. After completing the integration wizard, you must work with the Lyris Professional team to complete the integration to your Lyris HQ account and facilitate testing.
1. Add URL Query String Parameters: Verify that the URL append string is properly input into the Organization settings areas of the user interface. This should contain the campaign level ID (hq_m) and recipient level ID (hq_v).

   An example of a string ID is: 

   ```
   hq_lid=149&hq_m=96843&hq_l=23&hq_v=7703a51905
   ```

   >[!NOTE]
   >
   >If you are applying Lyris’s native analytics tool, *Click Tracks* tags all of the required variables that are added.

