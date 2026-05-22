---
description: How to view current server call usage in Adobe Analytics.
title: View current server call usage
feature: Server Call Usage
exl-id: 07eac732-b9d6-41ab-be34-5688eaa8166e
role: Admin
TQID: 'https://experienceleague.adobe.com/5DgWR4QWklOEMK1Ato17-lcpMdnRgaIrMfds9ATXUpE'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: c9d85838-8d05-4bc7-9f18-30ec779251bc
    internal-label: Server call usage
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# View current server call usage

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Server Call Usage]** > **[!UICONTROL Current Usage]** 

>[!IMPORTANT]
>
>Any usage and commitment numbers you see are cumulative across all your login companies and report suites.

The Current Usage dashboard

* Shows a breakdown of your server call consumption and commitment across each of your server-call types. This view could be different for different customers and is consistent with what your contract includes. For instance, you may have signed up for 4 separate types of server calls, Primary and Secondary for Web and Primary and Secondary for Mobile. In that case, this view would comprise 4 tabs, one for each type. Within each tab, you will be able to view the consumption for the current usage period.
* Compares current usage (green line) to your contractual usage limit (red line).

  ![](/help/admin/tools/server-call-usage/assets/current_period.png)

* Compares your current period's usage to last year's usage (blue line). Obviously, the blue line will only appear if your company has server call usage data from the previous year.

  >[!NOTE]
  >
  >If you want to view usage for a previous time period, you have to go to the [Report Suite Usage](/help/admin/tools/server-call-usage/report-suite-usage.md) tab and download the usage data for a previous period.

* Lists the percentage of calls used (in percentages and raw data), and the percentage of the usage period spent (in percentages and raw data).
* By default, is updated daily, with a 5-day processing latency.
* Lets you collapse and expand all reportlets.

![](/help/admin/tools/server-call-usage/assets/server_call_dashboard.png)

|  UI Term  | Definition  |
| --- | --- |
|  Current Period Usage (green)  |The current period is based on the [usage period](/help/admin/tools/server-call-usage/overage-overview.md).  |
|  Previous Period Usage (blue)  | The previous period is defined as the current usage period minus 1 year.  |
|  Usage Limit (red)  | Your contractual usage limit for this usage period.  |
