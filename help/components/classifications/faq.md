---
title: Classifications FAQ
description: Frequently asked questions for using classifications.
---

# Classifications FAQ

Frequently asked questions for using classifications.

## How do I classify the dimension item "0"?

Classification files uploaded with either a key value or classification value of zero (`0`) results in an error. It includes all values that only contain zeroes (`00`, `000`, and so on). There are several methods to resolve this issue:

* **Implement alternative values**: Using a text value other than `"0"` is the best and easiest way to resolve this issue. For example, change `s.campaign = "0";` in your implementation to `s.campaign = "Zero";`.

* **Use processing rules**: You can modify dimension items between data collection and their storage in a report suite. Create the following processing rule:
  
  *If [dimension] equals `0`, overwrite value of [dimension] with custom value `Zero`.*

* **Request a VISTA rule**: An Engineering Services consultant sets up a server-side rule for you at an extra cost. Contact your organization's Account Manager to request a VISTA rule.

## Can I use the uploader to classify dimension items that don't yet exist?

Yes, *however doing so counts each dimension item as a billable server call.*

* Dimension items that already exist do not incur any extra cost.
* Using the classification rule builder does not classify non-existent items, and therefore does not incur any extra cost.
