---
description: The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports. An eVar can be visit-based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.
keywords: eVar
title: Conversion Variables (eVar)
feature: Admin Tools
role: Admin
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
TQID: https://experienceleague.adobe.com/rYLxVYB1oDyfEk8gQyesTSRRPHid-6zJ8QaqFG2b0Kc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Conversion Variables (eVars)

The Custom Insight Conversion Variable (or eVar) is placed in the Adobe code on selected web pages of your site. Its primary purpose is to segment conversion success metrics in custom marketing reports. An eVar can be visit-based and function similarly to cookies. Values passed into eVar variables follow the user for a predetermined period of time.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**

## Conversion Variables (eVars) overview

For a video overview of conversion variables, see [Introduction to conversion variables](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/dimensions/introduction-to-conversion-variables-evars) in the Analytics tutorials guide.

When an eVar is set to a value for a visitor, Adobe automatically remembers that value until it expires. Any success events that a visitor encounters while the eVar value is active are counted toward the eVar value.

eVars are best used to measure cause and effect, such as:

* Which internal campaigns influenced revenue
* Which banner ads ultimately resulted in a registration
* The number of times an internal search was used before making an order

If traffic measurement or pathing is desired, using traffic variables is recommended.

>[!NOTE]
>
>Only a single value can be stored in an eVar in an image request. If multiple values are desired in an eVar value, use [List variables](/help/implement/vars/page-vars/page-variables.md).

### Conversion Variables - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

| Element | Description |
| --- | --- |
| [!UICONTROL Status] | Determines whether the eVar is active:<ul><li>**[!UICONTROL Enabled]**: The eVar is active.</li><li>**[!UICONTROL Disabled]**: Disables the eVar and removes it from the conversion variable list.</li></ul> |
| [!UICONTROL Description] | An optional description of the eVar. Use it to document what the eVar captures and how it is implemented. |
| [!UICONTROL Name] | The friendly dimension name of the conversion variable. It is how the eVar is referred to in general reporting. |
| [!UICONTROL Allocation] | Determines how Analytics assigns credit for a success event if a variable receives multiple values before the event. Supported values include:<ul><li>**[!UICONTROL Most Recent (Last)]**: The last eVar value always receives credit for success events until that eVar expires.</li><li>**[!UICONTROL Original Value (First)]**: The first eVar always receives credit for success events until that eVar expires.</li><li>**[!UICONTROL Linear]**: Allocates success events equally across all eVar values. Since Linear allocation distributes values only within a visit, use Linear allocation with an eVar expiration of Visit or shorter. This option is not available for merchandising eVars.</li></ul>**Important**: Adobe advises against switching to or from [!UICONTROL Linear] allocation, as it hides historical data in reporting until you switch back. To change allocation on an eVar with significant history, Adobe recommends using a new eVar instead. |
| [!UICONTROL Expire After] | Specifies when the eVar value expires (no longer receives credit for success events). If a success event occurs after eVar expiration, the None value receives credit for the event (no eVar was active). Supported values include:<ul><li>**[!UICONTROL Visit]**: The value expires at the end of the visit.</li><li>**[!UICONTROL Hit]**: The value applies only to the hit on which it is set.</li><li>**[!UICONTROL Minute]**, **[!UICONTROL Hour]**, **[!UICONTROL Day]**, **[!UICONTROL Week]**, **[!UICONTROL Month]**, **[!UICONTROL Quarter]**, or **[!UICONTROL Year]**: The value expires a fixed amount of time after it was set, to the second:<ul><li>Minute = 60 seconds</li><li>Hour = 3600 seconds (60 minutes)</li><li>Day = 86400 seconds (24 hours)</li><li>Week = 604800 seconds (7 days)</li><li>Month = 2678400 seconds (31 days)</li><li>Quarter = 8035200 seconds (93 days - 3 months of 31 days)</li><li>Year = 31536000 seconds (365 days)</li></ul>For example, if an eVar is set at 7:15 AM on Monday, [!UICONTROL Day] expiration ends at 7:15 AM on Tuesday, [!UICONTROL Week] expiration ends at 7:15 AM the following Monday, and [!UICONTROL Month] expiration ends 31 days later at 7:15 AM.</li><li>**[!UICONTROL Custom]**: The value expires after the number of days that you enter (86400 seconds per day).</li><li>**An event** ([!UICONTROL Purchase], [!UICONTROL Product View], [!UICONTROL Cart Open], [!UICONTROL Cart Checkout], [!UICONTROL Cart Add], [!UICONTROL Cart Remove], [!UICONTROL Cart View], or a custom event): The value expires when the selected event occurs. If the event never occurs, the value never expires.</li><li>**[!UICONTROL Never]**: As long as a visitor uses the same identifier, any amount of time can pass between the eVar and event.</li></ul> |
| [!UICONTROL Type] | The type of variable value:<ul><li>**[!UICONTROL Text String]**: Captures text values. It is the most common type of eVar, and the default setting. It acts similar to other variables, where the value within it is a static text string. If you track things such as internal campaigns or internal search keywords, this setting is recommended.</li><li>**[!UICONTROL Counter]**: Counts the number of times an action occurs before the success event. For example, you can count the number of searches made, regardless of search terms used, prior to a success event.</li></ul> |
| [!UICONTROL Reset] | On save, immediately expires all server-side persisted values for this variable across all visitors, including merchandising product bindings. Use [!UICONTROL Reset] when repurposing an eVar so you do not mix an old value into a new report. **Resetting does not erase historical data.** |
| [!UICONTROL Enable Merchandising] | Supported values include:<ul><li>**[!UICONTROL Disabled]**: The eVar credits success events to the value that persists for the visitor.</li><li>**[!UICONTROL Enabled]**: The eVar becomes a merchandising eVar, which binds values to individual products. Success events for each product are credited to the value bound to that product. Enabling merchandising shows the [!UICONTROL Merchandising] and [!UICONTROL Merchandising Binding Event] settings, and removes [!UICONTROL Linear] allocation.</li></ul>Enable merchandising only for eVars that describe how products are found or bought. A merchandising eVar no longer credits success events that aren't tied to a product. See [eVar (Merchandising)](/help/components/dimensions/evar-merchandising.md). |
| [!UICONTROL Merchandising] | Determines where the value to bind to products comes from:<ul><li>**[!UICONTROL Product Syntax]**: The value is set on each product in the `products` variable, and binds to that product on that hit. Each product can have a different value. Binding events are not used, so [!UICONTROL Merchandising Binding Event] is disabled.</li><li>**[!UICONTROL Conversion Variable Syntax]**: The value is set in the eVar itself and persists as a staged value, always reflecting the most recent value sent regardless of [!UICONTROL Allocation]. The value binds to the products on a hit only if that hit contains a selected [!UICONTROL Merchandising Binding Event]. Every product on that hit receives the same value.</li></ul>Changing this setting without updating your implementation accordingly causes lost data. See [eVar (Merchandising variable)](/help/implement/vars/page-vars/evar-merchandising.md) for implementation details. |
| [!UICONTROL Merchandising Binding Event] | Available only when [!UICONTROL Merchandising] is set to [!UICONTROL Conversion Variable Syntax]. Determines which events or eVars bind the eVar's staged value to the products on the same hit. If you don't select a binding event, [!UICONTROL All] is used. Supported values include:<ul><li>**[!UICONTROL All]**: Any other event or eVar on the hit triggers binding. This setting is the default.</li><li>**[!UICONTROL Purchase Event]**, **[!UICONTROL Product View Event]**, **[!UICONTROL Cart Open Event]**, **[!UICONTROL Cart Checkout Event]**, **[!UICONTROL Cart Add Event]**, **[!UICONTROL Cart Remove Event]**, or **[!UICONTROL Cart View Event]**: Binding occurs on hits that contain the selected event.</li><li>**[!UICONTROL Campaign Event]**: Binding occurs on hits that contain an instance of the [Tracking code](/help/components/dimensions/tracking-code.md) dimension ([`campaign`](/help/implement/vars/page-vars/campaign.md) variable).</li><li>**A custom event**: Binding occurs on hits that contain the selected custom event.</li><li>**A custom eVar**: Binding occurs on hits that set the selected eVar.</li></ul>Props cannot trigger binding. Select multiple values by holding down ctrl (Windows) or cmd (Mac) and clicking multiple items in the list. When a specific product that is already bound to an eVar receives another binding with that same eVar, [!UICONTROL Allocation] determines which value is kept. |

### Expiration

`eVars` expire after a time period you specify. After the eVar expires, it no longer receives credit for success events. eVars can also be configured to expire on success events. For example, if you have an internal promotion that expires at the end of a visit, the internal promotion receives credit only for purchases or registrations that occur during the visit in which they were activated.

There are two ways to expire an eVar:

* You can set the eVar to expire after a specified time period or event.
* You can force the expiration of an eVar by resetting it, which is useful when repurposing a variable.

For example, if you change the expiration of an eVar from 30 to 90 days, eVar values collected will continue to persist for the duration of the new expiration set (in this case, 90 days). The system simply looks at the current expiration setting and the last set timestamp of the eVar value collected to determine expiration. Only the **[!UICONTROL Reset]** option expires values and does so immediately.

Another example: If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. Doing so will help keep internal promotion values out of June's reports.

### Case Sensitivity

eVars are not case sensitive. The upper or lower case used in reporting is based on the first value the backend system registers. This value could either be the first instance ever seen or vary by some time period (e.g., monthly), depending on the variety and quantity of data associated with the report suite.

### Counters

While eVars are most often used to hold string values, they may also be configured to act as counters. eVars are useful as counters when you are trying to count the number of actions a user takes before an event. For example, you may use an eVar to capture the number of internal searches before purchase. Each time a visitor searches, the eVar should contain a value of '+1.' If a visitor searches four times before a purchase, you will see an instance for each total count: 1.00, 2.00, 3.00, and 4.00. However, only the 4.00 receives credit for the purchase event (Orders and Revenue Metrics). Only positive numbers are allowed as values of an eVar counter.

## Add or edit conversion variables

1. Click **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Select a report suite.
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Conversion Variables]**.
1. On the [!UICONTROL Conversion Variables] page, click the **[!UICONTROL Expand]** icon [+] next to the conversion variable you want to modify.

   Or

   Click **[!UICONTROL Add New]** to add an unused eVar to the report suite.
1. Select the conversion variable fields you want to modify.

   See [Conversion Variables - Descriptions](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md#section_7C317BB0287A4B8EB0A1A4ECC40627BF). Some fields let you type directly in the field. Others let you select from a drop-down list of supported values.
1. Click **[!UICONTROL Save]**.
