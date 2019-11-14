---
description: Page variables directly populate a report, such as pageName, List Props, List Variables, and so on.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Page variables
topic:
uuid:
---

# timestamp

This variable lets you customize the timestamp of a hit similar to the AppMeasurement libraries for other platforms.

<!-- 

timestamp.xml

 -->

|  Max Size  | Debugger Parameter  | Reports Populated  | Default Value  |
|---|---|---|---|
|  4 bytes  | Date/Time  | Not reported directly.  | Set by data collection servers.  |

**Syntax** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>Additionally, if you enable timestamp support on a report suite to support offline tracking, all hits sent to this report suite from JavaScript must also have a timestamp manually set (using *`s.timestamp`*). You cannot send both time-stamped and non-time-stamped hits to the same report suite.
>
>You can also use the [Timestamps Optional](/help/implement/js-implementation/timestamps-overview.md)setting to mix timestamped and non-timestamped data in the same global report suite, send timestamped data from a mobile app to a global report suite, and upgrade apps to employ timestamps without having to create a new report suite.

**Timestamp Formats** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Timestamps must be in UNIX (seconds since Jan 1st 1970) or ISO-8601 format, with the following restrictions on the accepted ISO-8601 format:

* Both date and time must be provided, separated by "T" 
* The date must be a calendar date with full precision (year, month, and day). . Week dates and ordinal dates are not supported.
* The date can be in standard or extended format ( `YYYY-MM-DD` or `YYYYMMDD`), but they must include the hour and minute. Seconds are optional ( `HH:MM`, `HH:MM:SS`, `HHMM`, or `HHMMSS`). Fractional minutes and seconds can be passed in, but the fractional part is ignored.

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

UNIX timestamps continue to be supported (seconds since Jan 1st 1970).

**Examples** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

The following list contains examples of valid ISO-8601 format timestamps:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Configuration Settings** {#section_5275D206F2CB4009B3681E8C4457124A}

A report suite must be enabled to accept custom timestamps by Customer Care before you can use this variable. After custom timestamps are enabled, all hits sent to the report suite must contain a timestamp or they are discarded.

**Pitfalls, Questions, and Tips** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Timestamps are primarily used to track offline data on mobile platforms. Custom timestamps are typically disabled unless you are collecting both web and offline app data in the same report suite.
* Data is timestamped when offline data is enabled in the mobile SDK (default setting) or anytime a report suite is configured to accept timestamped data. Data collected offline may be sent hours or weeks after the date when the event originally occurred. These hits may be queued within the Analytics platform for minutes or hours longer than hits without timestamps:

    * For timestamped data sent in very near current time, the probable delay is 10-15 minutes.
    * For timestamped data sent in from yesterday, the probable delay is about 2 hours.
    * For timestamped data sent in that is older than yesterday, every day adds about 2 hours of delay, up to a maximum of 48 hours.

