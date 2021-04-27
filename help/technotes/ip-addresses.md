---
title: IPs and domains used by Adobe Analytics
description: If your organization's firewall blocks IP addresses that originate from Adobe, use this list to update your firewall settings.
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
---
# IPs and domains used by Adobe Analytics

Some firewall configurations block IP addresses originating from Adobe's data collection servers or servers responsible for accessing data. You can use this list of ranges to alter your organization's firewall settings to allow access and to send data from within your organization.

>[!IMPORTANT]
>
>While Adobe does its best to keep this document current, it cannot guarantee the list of IP ranges remain the same. Possible changes include growth and expansion of the business, an internet registry requires changes to Adobe's IP address space, or an internet service provider stops functioning.

## Allow dependent technology domains

Adobe Analytics uses the following hosts to improve performance and product experience. Adobe recommends adding these domains to your firewall's allowed list for an optimal experience using Adobe Analytics.

| Technology | Domain |
| --- | --- |
| Adobe Analytics domains | `adobe.com`, `adobe.net`, `adobe.io` |
| Adobe Analytics legacy domain | `omniture.com` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft Azure CDN | `aauicdnva7.azureedge.net` |

## Data collection and FTP IP address blocks

If your organization prefers to allow specific IP address ranges you can use the following table. All of the ranges in this section are included in the above table.

| Location | IP Range (CIDR Notation) |
| --- | --- |
| Amsterdam | `66.117.28.0/23` |
| Dallas | `205.219.231.0/24` |
| Dallas | `66.235.152.0/22` |
| Dallas | `66.235.140.0/22` |
| Dallas | `63.140.32.0/21` |
| Dallas | `172.82.208.0/22` |
| Hong Kong SAR of China | `66.117.24.0/22` |
| London | `66.235.156.0/24` |
| London | `66.235.148.0/23` |
| London | `63.140.40.0/22` |
| London | `208.67.41.0/24` |
| London | `192.243.254.0/23` |
| London | `192.243.244.0/22` |
| London | `185.34.188.0/23` |
| London | `130.248.152.0/21` |
| London | `172.82.224.0/21` |
| London | `172.82.232.0/21` |
| Oregon | `192.243.240.0/22` |
| Oregon | `192.243.232.0/21` |
| Oregon | `192.243.224.0/21` |
| Oregon | `130.248.160.0/21` |
| Oregon | `130.248.148.0/22` |
| Oregon | `172.82.192.0/21` |
| Oregon | `172.82.216.0/21` |
| Paris | `208.67.40.0/24` |
| Singapore | `66.235.150.0/24` |
| Singapore | `66.235.130.0/23` |
| Singapore | `63.140.44.0/22` |
| Singapore | `208.67.43.0/24` |
| Singapore | `172.82.240.0/22` |
| Singapore | `172.82.246.0/23` |
| Singapore | `172.82.248.0/21` |
| San Jose | `66.117.20.0/24` |
| San Jose | `66.235.132.0/22` |
| San Jose | `130.248.128.0/22` |
| San Jose | `192.243.248.0/23` |
| San Jose | `172.82.200.0/22` |
| San Jose | `66.235.136.0/22` |
| San Jose | `208.91.175.0/24` |
| San Jose | `208.91.174.0/24` |
| San Jose | `208.91.169.0/24` |
| Sydney | `216.104.216.0/23` |
| Tokyo | `66.235.159.0/24` |
| Tokyo | `66.117.21.0/24` |
| Tokyo | `63.140.52.0/24` |
| Tokyo | `63.140.50.0/23` |
| Virginia | `66.235.144.0/22` |
| Virginia | `208.77.138.0/23` |
| Virginia | `208.77.136.0/23` |
| Virginia | `192.243.250.0/23` |
| Virginia | `130.248.144.0/22` |
| Virginia | `172.82.204.0/22` |
| Virginia | `172.82.212.0/22` |
| Virginia | See AWS Hosts |

## AWS hosts

Adobe Analytics uses Amazon Web Services as part of its data collection process. The following table includes AWS hosts reserved for Adobe. These hosts are **not** included in the aggregate block range above.

| Location | Host |
| --- | --- |
| Australia | `13.238.77.77` |
| Australia | `52.62.21.192` |
| Australia | `54.66.152.159` |
| China | `52.81.111.133` |
| China | `140.179.22.22` |
| France | `15.237.76.117` |
| France | `15.237.136.106` |
| France | `35.181.18.61` |
| India | `65.0.114.116` |
| India | `65.0.115.179` |
| India | `65.0.25.111` |
| Ireland | `18.202.158.78` |
| Ireland | `54.72.205.114` |
| Ireland | `54.78.36.71` |
| Oregon | `44.233.255.254` |
| Oregon | `44.237.54.118` |
| Oregon | `44.238.157.95` |
| Singapore | `52.220.116.94` |
| Singapore | `52.76.68.91` |
| Singapore | `54.179.114.68` |
| Tokyo | `18.182.161.178` |
| Tokyo | `54.168.58.167` |
| Tokyo | `54.178.61.109` |
| Virginia | `3.213.168.181` |
| Virginia | `3.219.249.186` |
| Virginia | `3.220.129.153` |
| Virginia | `18.206.109.10` |
| Virginia | `18.211.197.67` |
| Virginia | `34.227.41.189` |
| Virginia | `34.228.124.176` |
| Virginia | `54.90.190.103` |
| Virginia | `54.174.149.161` |
