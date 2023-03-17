---
description: Data Warehouse provides a feature that allows you to extract a list of visitor IDs. These IDs are not cookie IDs, but IDs that you capture in one of your conversion variables. Although there are other ways to get at this information, the following example is a shortcut to generating a Data Warehouse request.
title: Use Case - Extracting Visitor IDs
feature: Admin Tools
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
---
# Use Case - Extracting Visitor IDs

Data Warehouse provides a feature that allows you to extract a list of visitor IDs. These IDs are not cookie IDs, but IDs that you capture in one of your conversion variables. Although there are other ways to get at this information, the following example is a shortcut to generating a Data Warehouse request.

For example, assume that your business sends marketing e-mails to customers and prospects. Each of these e-mail recipients has a unique ID in your e-mail system (such as *`EMAIL Contact ID`*). You set up your e-mails so that when contacts receive an e-mail and click one of its links, the visitor arrives at your website with a campaign ID and a unique EMAIL Contact ID. For example, your e-mail link may resolve to:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Setting these in conversion variables (eVars) allows you to see how each e-mail performed (through the campaign ID) and how often each e-mail recipient visited the site (through the EMAIL Contact ID).

Assume you are capturing these IDs. Most marketers want to segment their website behavior and then see if they can re-market to those who meet certain criteria. For example, you may want to send a re-marketing e-mail to all e-mail recipients who came to your site from the e-mail and viewed (or completed) a website form. To do this, find a way to identify the EMAIL Contact IDs of those completing the specific form.

One way to do this is to use a Conversion Subrelation report to break down the Form ID eVar value by the EMAIL Contact ID eVar. However, a pre-built feature is available to do this using Data Warehouse. This feature allows you to tell which eVar stores your Unique User IDs (EMAIL Contact ID in this case) and allows you to easily extract those IDs using data warehouse. By using this feature, you can automatically create a data warehouse request that pulls the Unique Visitor IDs for which you are interested.
