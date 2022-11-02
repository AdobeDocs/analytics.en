---
title: IPs and domains used by Adobe Analytics
description: If your organization's firewall blocks IP addresses that originate from Adobe, use this list to update your firewall settings.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
---
# IPs and domains used by Adobe Analytics

Some firewall configurations block IP addresses originating from Adobe's data collection servers or servers responsible for accessing data. You can use this list of ranges to alter your organization's firewall settings to allow access and to send data from within your organization. This page includes both inbound systems (such as data collection) and outbound systems (such as data feeds) that Adobe uses.

>[!IMPORTANT]
>
>While Adobe does its best to keep this document current, it cannot guarantee that the list of IP ranges remains the same. Possible changes include growth and expansion of the business, an internet registry requires changes to Adobe's IP address space, or an internet service provider stops functioning.

## Allow dependent technology domains

Adobe Analytics uses the following hosts to improve performance and product experience. Adobe recommends allowing these domains through your organization's firewall for an optimal experience using Adobe Analytics.

| Technology | Domain |
| --- | --- |
| Adobe Analytics domains | `adobe.com`, `adobe.net`, `adobe.io` |
| Adobe Analytics legacy domain | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

## All Adobe Analytics IP address blocks

The following table covers all Adobe owned IP addresses used for Adobe Analytics. They do not include all services hosted in public cloud.

| IP Block (CIDR Notation) |
| --- |
| `63.140.32.0/19` |
| `66.117.16.0/20` |
| `66.235.128.0/19` |
| `130.248.0.0/16` |
| `185.34.188.0/22` |

## Data collection and FTP IP address blocks

If your organization prefers to allow specific IP address ranges you can use the following table. All of the ranges in this section are included in the above table. FTP connections for Data Warehouse and Data Feeds only originate from the London, Oregon, and Singapore locations.

| Location | IP Range (CIDR Notation) |
| --- | --- |
| Australia | `63.140.55.0/24` |
| Australia | `63.140.56.0/23` |
| California | `63.140.32.0/23` |
| California | `63.140.34.0/24` |
| India | `66.117.20.0/24` |
| India | `66.117.22.0/23` |
| Japan | `130.248.130.0/23` |
| Japan | `130.248.169.0/23` |
| Japan | `63.140.50.0/23` |
| Japan | `66.117.31.0/24` |
| London | `66.235.156.0/24` |
| London | `185.34.188.0/22` |
| Oregon | `66.235.132.0/22` |
| Singapore | `130.248.170.0/23` |
| Singapore | `130.248.240.0/24` |
| Singapore | `63.140.44.0/22` |
| Singapore | `63.140.48.0/23` |
| Singapore | `66.117.30.0/24` |
| Virginia | `63.140.38.0/23` |
| Virginia | `63.140.54.0/24` |

## AWS hosts

Adobe Analytics uses Amazon Web Services as part of its data collection process. The following table includes AWS IPv4 host addresses reserved for Adobe. These hosts are **not** included in the aggregate block range above.

| Location | Host |
| --- | --- |
| China | `52.80.83.220` |
| China | `71.132.16.253` |
| France | `13.36.218.177` |
| France | `15.188.95.229` |
| France | `15.236.176.210` |
| France | `13.37.25.97` |
| France | `15.236.117.205` |
| France | `15.236.125.10` |
| Ireland | `54.74.170.177` |
| Ireland | `54.195.254.128` |
| Ireland | `54.220.133.225` |
| Oregon | `52.10.149.115` |
| Oregon | `52.40.172.46` |
| Oregon | `54.212.155.93` |
| Virginia | `3.216.131.23` |
| Virginia | `34.204.237.47` |
| Virginia | `54.163.234.74` |

The following table includes AWS IPv6 address blocks used by Adobe. These hosts are **not** included in the aggregate block range above.

| Location | Host |
| --- | --- |
| Australia | `2406:da1c:406:1a00::/56` |
| Australia | `2406:da1c:ce5:b400::/56` |
| California | `2600:1f1c:366:d900::/56` |
| India | `2406:da1a:f34:6a00::/56` |
| Ireland | `2a05:d018:309:600::/56` |
| Japan | `2406:da14:b07:ab00::/56` |
| Oregon | `2600:1f14:1eb:7d00::/56` |
| Oregon | `2600:1f14:9d3:2b00::/56` |
| Singapore | `2406:da18:6e8:1e00::/56` |
| Virginia | `2600:1f18:1a20:e800::/56` |
| Virginia | `2600:1f18:4fd:6000::/56` |
| Virginia | `2600:1f18:b00:e100::/56` |
| Virginia | `2600:1f18:d1f:bd00::/56` |
