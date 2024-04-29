---
title: IPs and domains used by Adobe Analytics
description: If your organization's firewall blocks IP addresses that originate from Adobe, use this list to update your firewall settings.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
---
# IPs and domains used by Adobe Analytics

Some firewall configurations block domains that Adobe Analytics rely on for its product interface. You can use this list of domains to alter your organization's network settings to allow product access from within your organization.

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

{style="table-layout:auto"}

## Adobe Experience Cloud IP address blocks

In addition to the above domains, Adobe Analytics relies on several IP address blocks for data collection and exporting reports.

See Adobe Experience Cloud IP addresses for the full list of IP ranges.

## China Performance Optimization IP addresses

The China Performance Optimization add-on package is an additional paid service that improves AppMeasurement data collection performance for visitors within China. Contact your Adobe Account Team to learn more about using this feature.

>[!IMPORTANT]
>
>China RDC is not available for Web SDK data collection. These servers apply to AppMeasurement libraries only.

Regional data collection servers in China use the following IP addresses:

| Location | Host |
| --- | --- |
| China | `52.80.168.159` |
| China | `52.80.199.104` |
| China | `54.223.199.8` |

{style="table-layout:auto"}
