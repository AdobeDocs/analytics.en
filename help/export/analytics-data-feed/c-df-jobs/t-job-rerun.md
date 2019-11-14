---
description: You can rerun one or more jobs from the Jobs list.
keywords: Data Feed;job;rerun
solution: Analytics
title: Rerun a job
uuid: 5caf95da-dd88-4b1a-a081-684f4fd1f714
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

