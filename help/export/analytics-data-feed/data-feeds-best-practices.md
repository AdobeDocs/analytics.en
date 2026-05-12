---
description: Learn about best practices for data feed processing and delivery in Analytics.
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Best Practices and General Information
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
TQID: https://experienceleague.adobe.com/-8EoregiCONFrXywjKP5zMdypH-FM67ij1nVfxupBdY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Data feeds best practices

Following are some best practices for data feed processing and delivery.

* Ensure that you communicate any anticipated traffic spikes ahead of time. Latency directly impacts processing time for data feeds. See [Schedule a traffic spike](/help/admin/tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide.

* Data feeds do not contain a service-level agreement unless explicitly stated in your contract with Adobe. Feeds are usually delivered within several hours after the reporting window passes, however can occasionally take up to 12 hours or more.

* Hourly feeds using multiple file delivery process the fastest. Consider using hourly multiple file feeds if a timely delivery is a high priority for your organization.

* If you automate your feed ingestion process, consider the possibility that hits and files can be transferred more than once. Your feed ingestion process needs to handle duplicate hits and duplicate files without erroring out or duplicating data. We recommend using the combination of the `hitid_high` and `hitid_low` columns to uniquely identify a hit.

  In rare cases, you may see duplicate `hitid_high` and `hitid_low` values. If this happens, confirm the file was not previously sent and processed. If only some of the rows in a file are duplicate, consider adding `visit_num` and `visit_page_num` to help determine uniqueness.

* If using FTP (not recommended) ensure that you have ample room on your FTP site. Remove files from the destination on a regular basis so that you don't inadvertently run out of disk space.

* If using sFTP (not recommended), do not read or delete files with a `.part` suffix. The `.part` suffix indicates the file is partially transferred. Once the file is transferred, the `.part` suffix disappears.