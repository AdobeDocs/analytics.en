---
title: Implement Adobe Analytics with AppMeasurement for JavaScript
description: Learn how to implement Adobe Analytics using JavaScript without a tag management system.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
TQID: https://experienceleague.adobe.com/QScNJBw6-Xn-gQCJBBxVT6melUpnyy6VIKrzvnDzJyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
    internal-label: Events
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Implement Adobe Analytics with AppMeasurement for JavaScript

AppMeasurement for JavaScript has historically been a common method to implement Adobe Analytics. However, with increasing popularity of Tag Management Systems, using [tags in Adobe Experience Platform](../launch/overview.md) is recommended.

A high-level overview of the implementation tasks: 

![How to implement Adobe Analytivs with AppMeasurement for Javascript, as described in this section.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Task</b></th><th style="width:20%"><b>More Information</b></th>
</tr>

<tr>
<td>1</td><td>Ensure you have <b>defined a report suite</b></td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td><td><b>Download the required JavaScript code for AppMeasurement</b> from Code Manager. Unzip the file.</td><td><a href="../../admin/tools/code-manager-admin.md">Code Manager</a></td>
</tr>

<tr>
<td>3</td><td><b>Add <code>AppMeasurement.js</code> to your website's template file</b>. The code contains the libraries required to send data to Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Define configuration variables within <code>AppMeasurement.js</code></b>. When the Analytics object is instantiated, these variables make sure that data collection settings are correct.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Configuration Variables</a></td>
</tr>

<tr>
<td>5</td><td><b>Define page-level variables within your site's page code</b>. These variables determine specific dimension and metrics sent to Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Page Variables</a></td>
</tr>

<tr>
<td>6</td><td><b>Send the data to Adobe using the <code>t()</code> method</b>, when all page variables are defined.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t() method</a></td>
</tr>

<tr>
<td>7</td><td><b>Extend and validate your implementation</b> before pushing it out to production.</b></td><td></td>
</tr>

</table>

## Additional resources

- [Variables, functions, methods, and plug-ins overview](../vars/overview.md)
