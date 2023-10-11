---
description: Special considerations when using A4T and Adobe Analytics virtual report suites
title: Virtual report suites and Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
---
# Virtual report suites and Analytics for Target (A4T)

Please consider these caveats when using virtual report suites in the context of Adobe Target:

* You cannot send data directly from Target to a virtual report suite, only to a real report suite.
* You can report on A4T activities within a virtual report suite. However, the A4T data is limited to those rows that match the virtual report suite segment (and any other segments applied). For example, if you created a virtual report suite for your EMEA customers, then the A4T data in that virtual report suite reflects only the Target data for your EMEA customers. 
* You cannot publish segments from a virtual report suite back to Target for activation.
