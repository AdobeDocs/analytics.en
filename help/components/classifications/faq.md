---
title: Classifications FAQ
description: Frequently asked questions for using classifications.
feature: Classifications
exl-id: e929d7cb-0bfd-46de-88d1-aea2b4b91911
---
# Classifications FAQ

Frequently asked questions for using classifications.

## How do I classify the dimension item "0"?

Classification files uploaded with either a key value or classification value of zero (`0`) results in an error. It includes all values that only contain zeroes (`00`, `000`, and so on). There are several methods to resolve this issue:

* **Implement alternative values**: Using a text value other than `"0"` is the best and easiest way to resolve this issue. For example, change `s.campaign = "0";` in your implementation to `s.campaign = "Zero";`.

* **Use processing rules**: You can modify dimension items between data collection and their storage in a report suite. Create the following processing rule:
  
  *If [dimension] equals `0`, overwrite value of [dimension] with custom value `Zero`.*

* **Request a VISTA rule**: An Engineering Services consultant sets up a server-side rule for you at an extra cost. Contact your organization's Account Manager to request a VISTA rule.

## Can I use the classification importer to classify dimension items that don't yet exist?

Yes, *however doing so counts each dimension item as a billable server call.*

* Dimension items that already exist do not incur any extra cost.
* Using the classification rule builder does not classify non-existent items, and therefore does not incur any extra cost.

## How do I classify values that contain special characters?

Using leading and trailing blank spaces in either classification data and hit data is not supported because Adobe Analytics will truncate the blank characters from these data.
  
Using special characters such as commas or double quotes in reporting is typically not recommended. However, in some cases their use is necessary. If your reporting values contain such characters that you choose to classify, use the following steps:

1. Log in to Adobe Analytics, then navigate to **[!UICONTROL Admin]** > **[!UICONTROL Classification importer]**.
2. Click the **[!UICONTROL Browser export]** tab.
3. Configure export settings, and make sure that 'Quote Output' is NOT selected.
4. Click **[!UICONTROL Export File]**, and open the downloaded file in a spreadsheet editor.
5. On line 1, locate cell C1, which contains the value `v:2.0`. Change the value to `v:2.1` and apply the desired classifications to the workbook.
6. Upload the file as you would any other classification.

## What are Numeric 2 classifications?

Numeric 2 classifications let you classify dimension items as time-based metrics. They were retired from the Adobe Analytics UI in July 2019.
