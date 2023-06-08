---
title: Data sources FAQ
description: Frequently asked questions around data sources.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
---
# Data sources FAQ

Frequently asked questions around data sources.

+++What is the cost to use data sources?
Data sources do not incur any charges, nor do they count towards server call usage. [Full processing data sources](full-processing-eol.md) counted towards server calls before their retirement.
+++

+++How do data sources impact attribution and expiration for eVars?
If a transactionID matches between a data source and an online hit, the associated eVar values assume the same attribution and expiration as if they were set on the online hit.

All other data uploaded through data sources do not have any kind of attribution or expiration.
+++

+++How do data sources impact default metrics, such as page views, visits, or unique visitors?
Data uploaded through data sources do not impact [Page views](/help/components/metrics/page-views.md), [Visits](/help/components/metrics/visits.md), or [Unique visitors](/help/components/metrics/unique-visitors.md) in any way. The only default metric that they impact includes [Occurrences](/help/components/metrics/occurrences.md).
+++

+++Can I delete data that was imported using data sources?

**No.** Data uploaded into reports using data sources is **permanent**. It cannot be removed, not even by Adobe, once it has been imported. Adobe strongly recommends uploading data sources data into a test report suite before uploading it into a production report suite.
+++

+++How much data can I import at a time?

Processing pauses if the size exceeds 50 MB and does not resume until the total is below 50 MB. Make sure that the total size of all files on the FTP site is less than 50 MB.
+++

+++What happens if I pass negative values into reporting through data sources?

The value is decreased accordingly. Some organizations use negative data source values to attempt to correct data. Negative data source values can impact reports in potentially undesired or unexpected ways. Adobe recommends using negative data sources only as a last resort.
+++

+++Are file extensions case-sensitive?
Yes. Files with an extension of `.TXT` or `.FIN` are not processed. Make sure that file extensions are all lowercase.
+++

+++How many columns can I add to a data source file?
You can include as many columns to a data source file as you'd like, if they are all valid columns. See [File format](file-format.md) for a list of valid variable/column names.
+++

+++Can I use data sources without using the Adobe-provided FTP location?
You can use the [Data sources API](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), which allows you to send API calls directly to Adobe. These API calls include an `UploadData` method, which allows you to send data by a JSON object payload.
+++
