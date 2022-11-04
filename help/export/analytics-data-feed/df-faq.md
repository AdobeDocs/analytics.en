---
description: Frequently asked questions about data feeds
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Data feeds FAQ
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
---
# Data feeds FAQ

Frequently asked questions about data feeds.

## Must feed names be unique?{#unique}

Data feed file names are made up of the report suite ID and the date. Any two feeds that are configured for the same RSID and date(s) have the same file name. If those feeds are delivered to the same location, one file will overwrite the other. To prevent a file overwrite, you cannot create a feed that has the potential to overwrite an existing feed in the same location.

Trying to create a feed when another exists with the same file name results in an error message. Consider the following workarounds:

* Change the delivery path
* Change the dates if possible
* Change the report suite if possible

## When is data processed? {#processed}

Before processing hourly or daily data, data feeds waits until all the hits that entered data collection within the timeframe (day or hour) have been written out to data warehouse. After that occurs, data feeds collect the data with timestamps that fall within the timeframe, compresses it, and sends it via FTP. For hourly feeds, files are typically written out to data warehouse within 15-30 min after the hour, but there is no set time period. If there was no data with timestamps that fall within the timeframe, then the process tries again the next timeframe. The current data feed process uses the `date_time` field to determine which hits belong to the hour. This field is based on the time zone of the report suite.

## What is the difference between columns with a `post_` prefix and columns without a `post_` prefix? {#post}

Columns without the `post_` prefix contain data exactly as it was sent to data collection. Columns with a `post_` prefix contain the value after processing. Examples that can change a value are variable persistence, processing rules, VISTA rules, currency conversion, or other server-side logic Adobe applies. Adobe recommends using the `post_` version of a column where possible.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## How do data feeds handle case sensitivity? {#case}

In Adobe Analytics, most variables are considered as case-insensitive for reporting purposes. For example, 'snow', 'Snow', 'SNOW', and 'sNow' are all considered the same value. Case sensitivity is preserved in data feeds.

If you see different case variations of the same value between non-post and post columns (for example, 'snow' in the pre column and 'Snow' in the post column), your implementation uses both uppercase and lowercase values across your site. The case variation in the post column was previously passed in and is stored in the virtual cookie, or was processed around the same time for that report suite.

## Are bots filtered by Admin console bot rules included in data feeds? {#bots}

Data feeds do not include bots filtered by [Admin console bot rules](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Why do I see multiple `000` values in the `event_list` or `post_event_list` data feed column? {#values}

Some spreadsheet editors, especially Microsoft Excel, automatically round large numbers. The `event_list` column contains many comma-delimited numbers, sometimes causing Excel to treat it as a large number. It rounds the last several digits to `000`.

Adobe recommends against automatically opening `hit_data.tsv` files in Microsoft Excel. Instead, use Excel's Import Data dialog box and make sure that all fields are treated as text.

## Are columns like `hitid_high`, `hitid_low`, `visid_high`, and `visid_low` guaranteed to be unique to the hit or visit? {#hitid}

In almost all cases, the concatenation of `hitid_high` and `hitid_low` uniquely identify a hit. The same concept applies to the concatenation of `visid_high` and `visid_low` for visits. However, processing anomalies can rarely cause two hits to share the same hit ID. Adobe recommends against creating data feed workflows that inflexibly rely on every hit being unique.

## Why is information missing from the domain column for some carriers? {#domain}

Some mobile carriers (such as T-Mobile and O1) are no longer providing domain info for reverse-DNS lookups. Therefore, that data is not available for domain reporting.

## Why can't I extract "Hourly" files from data that is more than 7 days old? {#hourly}

For data that is more than 7 days old, a day's "Hourly" files are combined into a single "Daily" file.

Example: A new Data Feed is created on March 9, 2021, and the data from January 1, 2021 to March 9 is delivered as "Hourly". However, the "Hourly" files before March 2, 2021 are combined into a single "Daily" file. You can extract "Hourly" files only from data that is less than 7 days old from the creation date. In this case, from March 2 to the March 9.

## What is the impact of Daylight Savings on hourly data feeds? {#dst} 

For certain time zones, the time changes twice a year due to daylight saving time (DST) definitions. Data feeds honor the time zone for which the report suite is configured. If the time zone for the report suite is one that does not use DST, file delivery continues normally like any other day. If the time zone of the report suite is one that does use DST, file delivery is altered for the hour in which the time change occurs (usually 2:00 am).

When making STD -> DST time transitions ("Spring Forward"), the customer receives only 23 files. The hour that is skipped in the DST transition is omitted. For example, if the transition occurs at 2 AM, they get a file for the 1:00 hour and a file for the 3:00 hour. There is no 2:00 file because, at 2:00 STD, it becomes 3:00 DST.

When making DST -> STD transitions, ("Fall Back"), the customer gets 24 files. However, the hour of transition actually includes two hours' worth of data. For example, if the transition occurs at 2:00 am, the file for 1:00 is delayed by one hour, but it contains data for two hours. It contains data from 1:00 DST to 2:00 STD (which would have been 3:00 DST). The next file begins at 2:00 STD.

## How does Analytics handle FTP transfer failures? {#ftp-failure}

If an FTP transfer fails (because of a denied login, lost connection, out of quota error, or other issue), Adobe attempts to automatically connect and send the data up to three separate times. If the failures persist, the feed is marked as failed and an email notification is sent.

If a transfer fails, you can rerun a job until it succeeds.

If you have issues getting a data feed to appear on your FTP site, see [Troubleshoot data feeds](troubleshooting.md).

## How do I resend a job? {#resend}

Once you have verified/corrected the delivery issue, rerun the job to get the files.

## What is the BucketOwnerFullControl setting for Amazon S3 data feeds? {#BucketOwnerFullControl}

**BucketOwnerFullControl** provides cross-account rights to create objects in other buckets.

The common use case for Amazon S3 is that the Amazon Web Services (AWS) account owner creates a bucket, then creates a user that has permission to create objects in that bucket, and then provides credentials for that user. In this case, the objects of a user belong to the same account, and the account owner implicitly has full control of the object (read, delete, and so on). This process is similar to how FTP delivery works.

AWS also makes it possible for a user to create objects in a bucket that belong to a different user account. For example, say two AWS users, userA and userB, do not belong to the same AWS account but want to create objects in other buckets. If userA creates a bucket called "bucketA," they can create a bucket policy that explicitly allows userB to create objects in bucketA even though the user doesn't own the bucket. This policy can be advantageous because it doesn't require userA and userB to exchange credentials. Instead, userB provides userA with their account number, and userA creates a bucket policy that essentially says "let userB create objects in bucketA".

However, objects do not inherit permissions from the parent bucket. Therefore, if userB uploads an object to userA's bucket, userB still "owns" that object, and, by default, userA is not granted any permissions to that object even though userA owns the bucket. UserB must explicitly grant userA permissions because userB is still the object's owner. To grant this permission, userB must upload the object with a BucketOwnerFullControl ACL, which specifies that the bucket owner (userA) is granted full permissions to the object (read, write, delete, and so on), even though the object is "owned" by userB.

>[!NOTE]
>
>Adobe Analytics does not determine if the bucket has a policy that requires giving the bucket owner full control of new objects, or even if the bucket owner is in a different account than the user writing the data. Instead, Analytics automatically adds the bucket owner to the `BucketOwnerFullControl` ACL with each feed upload.

