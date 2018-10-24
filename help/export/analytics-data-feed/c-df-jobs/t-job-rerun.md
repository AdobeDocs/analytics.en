---
description: You can rerun one or more jobs from the Jobs list.
keywords: Data Feed;job;rerun
seo-description: You can rerun one or more jobs from the Jobs list.
seo-title: Rerun a job
solution: Analytics
title: Rerun a job
uuid: 4480f7c8-0c50-4550-91d7-526afd7bdc48
index: y
internal: n
snippet: y
---

# Rerun a job

You can rerun one or more jobs from the Jobs list.

1. Select one or more jobs that you want to rerun.
1. Click **[!UICONTROL Rerun Job]**.

   The rerun process depends on the current job status:

   |  Status  | Filename Cached on Server  | Process  |
   |---|---|---|
   |  Completed  | Yes  | File is resent.  |
   |  Completed  | No  | Job is reprocessed then resent.  |
   |  Failed  | No  | Job is reprocessed then resent.  |
   |  Other Status  | N/A  | Not supported.  |

