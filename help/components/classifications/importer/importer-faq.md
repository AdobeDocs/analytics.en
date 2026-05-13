---
title: Classifications FAQ
description: Frequently asked questions for using classifications.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
TQID: https://experienceleague.adobe.com/pIwAdewnHA4AB9hyRDRkH6xXvyxx-BceWvDXMydX-ew
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Classification importer FAQ

{{classification-importer-deprecation}}

Frequently asked questions for using the classification importer.

## How do I classify the dimension item "0"?

Classification files uploaded with either a key value or classification value of zero (`0`) results in an error. It includes all values that only contain zeroes (`00`, `000`, and so on). There are several methods to resolve this issue:

* **Implement alternative values**: Using a text value other than `"0"` is the best and easiest way to resolve this issue. For example, change `s.campaign = "0";` in your implementation to `s.campaign = "Zero";`.

* **Use processing rules**: You can modify dimension items between data collection and their storage in a report suite. Create the following processing rule:
  
  *If [dimension] equals `0`, overwrite value of [dimension] with custom value `Zero`.*

* **Request a VISTA rule**: An Engineering Services consultant sets up a server-side rule for you at an extra cost. Contact your Adobe Account Team to request a VISTA rule.

## Can I use the classification importer to classify dimension items that don't yet exist?

Yes, *however doing so counts each dimension item as a billable server call.*

* Dimension items that already exist do not incur any extra cost.
* Using the classification rule builder does not classify non-existent items, and therefore does not incur any extra cost.

## How do I classify values that contain special characters?

Using leading and trailing blank spaces in either classification data and hit data is not supported because Adobe Analytics automatically truncates blank characters.
  
Using special characters such as commas or double quotes in reporting is typically not recommended. However, in some cases their use is necessary. If your reporting values contain such characters that you choose to classify, use the following steps:

1. Log in to Adobe Analytics, then navigate to **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Click the **[!UICONTROL Browser export]** tab.
3. Configure export settings, and make sure that 'Quote Output' is NOT selected.
4. Click **[!UICONTROL Export File]**, and open the downloaded file in a spreadsheet editor.
5. On line 1, locate cell C1, which contains the value `v:2.0`. Change the value to `v:2.1` and apply the desired classifications to the workbook.
6. Upload the file as you would any other classification.

## What are Numeric 2 classifications?

Numeric 2 classifications let you classify dimension items as time-based metrics. They were retired from the Adobe Analytics UI in July 2019.

## How can I escape data in a classification file?

Surround the field containing special characters in double quotes (`"`). A double quote character can appear in an escaped cell by replacing it with two double quote characters (`" "`). For example:

```
My String "of data"
```

Escaped would be:

```
"My String ""of data"""
```
