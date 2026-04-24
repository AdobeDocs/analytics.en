---
description: Special considerations when using A4T and Adobe Analytics virtual report suites
title: Virtual report suites and Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Virtual report suites and Analytics for Target (A4T)

Please consider these caveats when using virtual report suites in the context of Adobe Target:

* You cannot send data directly from Target to a virtual report suite, only to a real report suite.
* You can report on A4T activities within a virtual report suite. However, the A4T data is limited to those rows that match the virtual report suite segment (and any other segments applied). For example, if you created a virtual report suite for your EMEA customers, then the A4T data in that virtual report suite reflects only the Target data for your EMEA customers. 
* You cannot publish segments from a virtual report suite back to Target for activation.
