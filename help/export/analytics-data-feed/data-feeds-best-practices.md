---
description: Following are some best practices for data feed processing and delivery. You should 
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Best Practices and General Information
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
---

# Best Practices

Following are some best practices for data feed processing and delivery.

* Ensure that you communicate any anticipated traffic spikes ahead of time. Latency directly impacts processing time for data feeds. See [Schedule a traffic spike](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide.
* Data feeds do not contain a service-level agreement unless explicitly stated in your contract with Adobe. Feeds are usually delivered within several hours after the reporting window passes, however can occasionally take up to 12 hours or more.
* Ensure that you have ample room on your FTP site. Remove files from the destination on a regular basis so that you don't inadvertently run out of disk space.
* Hourly feeds using multiple file delivery process the fastest. Consider using hourly multiple file feeds if a timely delivery is a high priority for your organization.
* If using sFTP, do not read or delete files with a `.part` suffix. The `.part` suffix indicates the file is partially transferred. Once the file is transferred, the `.part` suffix disappears.
* If you automate your feed ingestion process, consider the possibility that a file can be transferred more than once. Duplicate files can be resent by the user or rarely by Adobe.
