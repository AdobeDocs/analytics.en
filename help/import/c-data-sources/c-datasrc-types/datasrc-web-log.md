---
description: Web Log data sources let you import standard web server log files.
subtopic: Data sources
title: Web log
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
---
# Web log

Web Log data sources let you import standard web server log files.

The following common web server log types are supported: 

| Column Name  |  Description  |
|--- |--- |
|NCSA Common Log|Apache Default|
|NCSA Extended (Combined)|Apache|
|W3C Extended Log|Used by IIS 4.0 and later|
|Microsoft IIS Log|Used by IIS 3.0 and earlier|

The primary log file fields that Data Sources processes include IP Address, Date/Time of the request, and the URL. In a few cases, such as the NCSA Extended format, Data Sources also processes the Referrer and the User Agent fields.

You can view web log data using standard marketing reports for Page Views, Visits, and Visitors. Because report metrics are primarily based on cookies, and web server logs are based on the IP address, Adobe recommends importing the web server logs into a separate report suite specifically for that purpose.

For more information about your web server log files, consult your web server documentation.
