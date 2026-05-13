---
title: IP addresses used by Adobe Analytics
description: If your organization's firewall blocks IP addresses that originate from Adobe, use this list to update your firewall settings.
feature: Data Configuration and Collection
exl-id: e24a70e4-9ed4-4b87-8bab-4ed0aebedd1f
TQID: https://experienceleague.adobe.com/-4XZdprTBXpIaFnHeXBQsAr5YoZMW4ocnZRY50bHGUs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# IP addresses used by Adobe Analytics

Some firewall configurations block IP addresses originating from Adobe's data collection servers or servers responsible for accessing data. You can use this list of ranges to alter your organization's firewall settings to allow access and to send data from within your organization. 

All IP addresses used by Adobe Analytics are part of [IP addresses used by the Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses), with exception to the China Performance Optimization add-on package.

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

>[!MORELIKETHIS]
>
>[IP addresses used by the Adobe Experience Cloud](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/ip-addresses)
>
>[Domains used by Adobe Analytics](domains.md)
