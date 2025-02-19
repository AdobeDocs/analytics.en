---
description: Use alerts in Analysis Workspace.
title: Alert Builder overview
feature: Alerts
exl-id: 82e51357-4a32-4db1-bc56-95a72dbaa1be
---
# Create alerts {#create-alerts}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_alerts_timegranularity"
>title="Time granularity"
>abstract="Time granularity refers to both how often the alert will be checked and what will be included"

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>Using alerts with anomaly detection (also known as _Intelligent Alerts_) is available only to organizations with an Adobe Analytics Prime or Ultimate package.

Alerts in Adobe Analytics allow you to be notified based on changed percentages or specific data points. Depending on your Adobe Analytics package, you can also use alerts to be triggered based on anomaly thresholds. Server call usage alerts are a different kind of alert that is available only to Analytics administrators. These alerts notify you of the risk or occurrence of an overage in your server call consumption and commitment data. For more information, see [Server call usage alerts](/help/admin/admin/c-server-call-usage/scu-alerts.md).

For more detailed overview information about alerts, see [Alerts overview](/help/components/c-alerts/intellligent-alerts.md).

To create an alert:

1. Begin creating an alert by accessing the alert builder. You can access the alert builder in any of the following ways:

   * Open a project in Analysis Workspace, then select **[!UICONTROL Components]** > **[!UICONTROL Create alert]**.
   * Open a project in Analysis Workspace, then use the following shortcut: ***ctrl (or cmd) + shift + a***. 
   * Open a project in Analysis Workspace, select one or more line items in a freeform table, then right-click and select **[!UICONTROL Create alert from selection]**. This action instantly pre-populates the alert builder to create an alert with the correct metrics and filters.
   * Create an alert [from the alert manager](/help/components/c-alerts/alert-manager.md#create-alerts). 

   The alert builder displays. This interface is familiar to the interface to build segments or calculated metrics in Analytics:

   ![](assets/alert-builder.png)

1. Specify the following options to configure the alert:

   | Option | Description | 
   |---------|----------|
   | [!UICONTROL **Title**]  | Specify a name for the alert. The alert name might contain the name of the report or the metrics threshold. | 
   | [!UICONTROL **Description (optional)**] | Specify a description for the alert. | 
   | [!UICONTROL **Time granularity**] | Select how often you want the metric to be checked: Hourly, Daily, Weekly, or Monthly.<p><b>Note:</b> For report suites with a custom calendar, monthly granularity in the Alert Builder is not supported.<!--true?--></p> | 
   | [!UICONTROL **Recipients**] | Specify where the alert can be sent. An alert can be sent to an Analytics user, an Analytics group, a raw email address, or to a phone number.<p><b>Important:</b> The phone number must be preceded by `+` and a [country code](https://countrycode.org/).</p><p>The e-mail that a user would receive once an alert has been triggered looks similar to:</p><p>![](assets/alerts-email.PNG)</p> | 
   | [!UICONTROL **Expiration date**] | Set the date and time when you want the alert to expire. | 
   | [!UICONTROL **Send an alert when**] | [!UICONTROL **Any of these metrics trigger**]: Drag and drop metrics (including calculated metrics) here to create triggers for the alert.<p>An **"incompatible components"** message appears if not all the metrics, dimensions, or segments in the alert are compatible with the currently selected data view.</p><p>Determine the threshold that the metric must exceed before an alert is set. You can set this value to a threshold and then to one of the following conditions:</p><ul><li>anomaly exists</li><li>anomaly is above expected</li><li>anomaly is below expected</li><li>is above or equals</li><li>is below or equals</li><li>changes by</li><li>You can set a threshold of 90%, 95%, 99%, 99.75%, and 99.9%.</li></ul><p>[!UICONTROL **With all of these filters**]: Drag and drop segments or dimensions to add filters. For example, adding a "Mobile Devices Only" segment would mean that the rule triggers only for mobile devices. You can add additional filters by using an AND statement. You can add AND or OR rules by clicking the gear icon.</p><p>See [Alerts - use cases](/help/components/c-alerts/alerts-use-cases.md) for example.</p> | 
   | [!UICONTROL **Preview**] | The interactive alert preview shows you how often, approximately, an alert will fire based on past experience.<p>For example, if you set the time granularity to daily, the preview can tell you that the alert would have been triggered for a certain metric x times during the last 30 or 31 days. The preview approximation window is established by the alert frequency setting. For daily alert frequencies, the preview window approximates the previous 30 days. For weekly alert frequencies, the preview window approximates the last 12 weeks. For monthly alert frequencies, the preview window approximates the previous 12 months.</p><p>If you find that too many alerts will be triggered, you can adjust the threshold in the [Alert Manager](/help/components/c-alerts/alert-manager.md).</p><p>![](assets/alert_preview.png)</p> |

1. Select [!UICONTROL **Save**].
