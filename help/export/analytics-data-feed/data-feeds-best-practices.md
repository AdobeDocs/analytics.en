---
description: Following are some best practices for data feed processing and delivery.
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Best Practices and General Information
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
---
# Best Practices

Following are some best practices for data feed processing and delivery.

* Ensure that you communicate any anticipated traffic spikes ahead of time. Latency directly impacts processing time for data feeds. See [Schedule a traffic spike](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide.

* Data feeds do not contain a service-level agreement unless explicitly stated in your contract with Adobe. Feeds are usually delivered within several hours after the reporting window passes, however can occasionally take up to 12 hours or more.

* Ensure that you have ample room on your FTP site. Remove files from the destination on a regular basis so that you don't inadvertently run out of disk space.

* Hourly feeds using multiple file delivery process the fastest. Consider using hourly multiple file feeds if a timely delivery is a high priority for your organization.

* If using sFTP, do not read or delete files with a `.part` suffix. The `.part` suffix indicates the file is partially transferred. Once the file is transferred, the `.part` suffix disappears.

* If you automate your feed ingestion process, consider the possibility that hits and files can be transferred more than once. Your feed ingestion process needs to handle duplicate hits and duplicate files without erroring out or duplicating data. We recommend using the combination of the `hitid_high` and `hitid_low` columns to uniquely identify a hit.

  In rare cases, you may see duplicate `hitid_high` and `hitid_low` values. If this happens, confirm the file was not previously sent and processed. If only some of the rows in a file are duplicate, consider adding `visit_num` and `visit_page_num` to help determine uniqueness.
