---
description: This section contains information about common issues.
keywords: Data Feed;troubleshooting
seo-description: This section contains information about common issues.
seo-title: Troubleshoot Data Feeds
solution: Analytics
title: Troubleshoot Data Feeds
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
---

# Troubleshoot Data Feeds

This section contains information about common issues.

## Error When Saving Feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

Data feed file names are made up of the report suite ID and the date. Any two feeds that are configured for the same RSID and date(s) will have the same file name. If those feeds are delivered to the same location, one file would overwrite the other. To prevent a file overwrite, you cannot create a feed that has the potential to overwrite an existing feed in the same location.

Trying to create a feed when another exists with the same file name results in the following message:

If you receive this error, consider the following workarounds:

* Change the delivery path 
* Change the dates if possible 
* Change the report suite if possible

## BucketOwnerFullControl setting for Amazon S3 data feeds {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

The common use case for Amazon S3 is that the Amazon Web Services (AWS) account owner creates a bucket, then creates a user that has permission to create objects in that bucket, and then provides credentials for that user. In this case, the objects of a user belongs to the same account, and the account owner implicitly has full control of the object (read, delete, etc). This is similar to how FTP delivery works.

AWS also makes it possible for a user to create objects in a bucket that belong to a completely different user account. For example, if two AWS users, userA and userB, do not belong to the same AWS account but want to create objects in other buckets. If userA creates a bucket, say bucketA, he or she can create a bucket policy that explicitly allows userB to create objects in bucketA even though the user doesn't own the bucket. This can be advantageous because it doesn't require that userA and userB to exchange credentials. Instead, userB provides userA with their account number, and userA creates a bucket policy that essentially says "let userB create objects in bucketA".

**BucketOwnerFullControl** provides cross-account rights to create objects in other buckets. If userB uploads an object to userA's bucket, userB still "owns" that object, and by default, userA is not granted any permissions to that object even though userA owns the bucket—objects do not inherit permissions from the parent bucket. UserB must explicitly grant userA permissions because userB is still the object's owner. For this cross-account upload, AWS provides a BucketOwnerFullControl ACL by specifying that the use of this ACL by the bucket owner (userA) and is granted full permissions to the object (read, write, delete, etc), even though the object is "owned" by userB.

## Transfer Failures {#section_4BD44E9167F0494FB2B379D2BA132AD8}

In the event of an FTP transfer failure (login denied, lost connection, out of quota, etc), Adobe attempts to automatically connect and send the data up to three separate times. If the failures persist, the feed is marked as failed and an email notification is sent.

In case of a transfer failure, you can [rerun a job](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) until it succeeds.

## Resend Options {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Once you have verified/corrected the delivery issue, just use [rerun the job](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) to get the files.

## Daylight Savings impact on Hourly Data Feeds {#section_70E867D942054DD09048E027A9474FFD}

For certain time zones the time will change twice a year due to daylight saving time (DST) definitions. Data feeds honor the time zone for which the report suite is configured. If the time zone for the report suite is one that does not use DST, file delivery will continue normally like any other day. If the time zone of the report suite is one that does use DST, file delivery will be altered for the hour in which the time change occurs (usually 2:00 am).

When making STD -> DST time transitions (“Spring Forward”), the customer will only get 23 files. The hour that is skipped in the DST transition is simply omitted. For example, if the transition occurs at 2 AM, they’ll get a file for the 1:00 hour, and will get a file for the 3:00 hour. There will be no 2:00 file, since at 2:00 STD, it becomes 3:00 DST.

When making DST -> STD transitions, (“Fall Back”), the customer will get 24 files. However, the hour of transition will actually include 2 hours’ worth of data. For example, if the transition occurs at 2:00 am, the file for 1:00 will be delayed by one hour, but will contain data for two hours. It will contain data from 1:00 DST to 2:00 STD (which would have been 3:00 DST). The next file will begin at 2:00 STD.

## No Data for a Time Period {#section_72510794694D42A9A75C966B812AEB0F}

You can optionally configure a data feed to deliver a manifest file if no data is collected for a specific period. If you enable this option, you'll receive a manifest file similar to the following:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## No Domain Info for Domain Reporting {#section_B7508D65370442C7A314EAED711A2C75}

Some mobile carriers (such as T-Mobile and O1) are no longer providing domain info for reverse-DNS lookups. Therefore, that data is not available for domain reporting.

## Data Processing Overview {#section_6346328F8D8848A7B81474229481D404}

Before processing hourly or daily data, data feeds waits until all the hits that entered data collection within the timeframe (day or hour) have been written out to data warehouse. After that occurs, data feeds collects the data with timestamps that fall within the timeframe, compresses it, and sends it via FTP. For hourly feeds, files are typically written out to data warehouse within 15-30 min after the hour, but there is no set time period. If there was no data with timestamps that fall within the timeframe, then the process tries again the next timeframe. The current data feed process uses the `date_time` field to determine which hits belong to the hour. This field is based on the time zone of the report suite. 
