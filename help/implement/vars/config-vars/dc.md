---
title: dc
description: A retired variable that let you determine which data center to use.
---

# dc

>[!IMPORTANT] This variable is retired. Use [`trackingServer`](trackingserver.md) instead.

In previous versions of Adobe Analytics, Adobe required that you specify which data center you wanted to send data to. Sending hits to the wrong data center resulted in data loss.

Adobe has improved this experience by allowing any implementation to send hits to `sc.omtrdc.net`. Specifying data center is no longer needed.
