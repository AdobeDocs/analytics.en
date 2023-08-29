---
description: Describes how Report Builder supports pathing and fallout reports and how the implementation differs from Reports & Analytics.
title: Path and path fallout reports in Report Builder
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
---
# Path and path fallout reports in Report Builder

Describes how Report Builder supports pathing and fallout reports and how the implementation differs from Reports & Analytics.

|Path Report Name in Reports & Analytics (Paths >  dimension >)  | Supported in Report Builder? |
|--- |--- |
|Next/Previous  dimension Flow|Not provided as a standalone report. Can be reproduced with several requests with the Path dimension and using a filter.|
|Next/Previous  dimension|Not provided as a standalone report. Can be reproduced with a Path report and using a filter.|
|Fallout|Supported and provided as a standalone report ( Paths >  dimension >  dimension  Fallout).|
|Full Paths|Not supported.|
|PathFinder|Not provided as a standalone report. Can be reproduced as a Path report using a filter.|
|Path Length|Supported only for the Page dimension.|
|Page Analysis >  dimension Summary|Not provided as a standalone report. Can be reproduced with several requests with the Path dimension and using a filter.|
|Page Analysis > Reloads|Not provided as a standalone report. Can be reproduced with a dimension report using the  Reloads metric.|
|Page Analysis >  dimension Depth|Supported only for the Page dimension.|
|Page Analysis > Time Spent on  dimension|Not supported.|
|Entries and Exits > Entry Pages|Not provided as a standalone report. Can be reproduced as a Path report using the pre-defined filter  Entered Site.|
|Entries and Exits > Original Entry Pages|Supported only for the Page dimension.|
|Entries and Exits > Single Page Visits|Not provided as a standalone report. Can be reproduced as a Path report using a pre-defined filter.|
|Entries and Exits > Exit  dimension|Not provided as a standalone report. Can be reproduced as a Path report using the pre-defined filter  Exited Site.|
