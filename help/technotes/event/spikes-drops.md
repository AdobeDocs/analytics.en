---
title: Troubleshoot spikes and drops in data
description: Learn possible reasons why you can see dramatic increases or decreases in trended reports.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
---
# Troubleshoot spikes and drops in data

As your site collects data, there are many external factors that can drastically affect data collection or reporting. The following is a list of potential explanations as to why certain variables or overall traffic dramatically increases or decreases.

As you determine the cause and move toward a resolution, you can gauge the impact of the event on your data, and determine how you want to proceed. See the [overview page](overview.md) for more information.

## Traffic drops

Traffic drops are categorized into two sections: partial data and zero data.

### Potential causes of completely missing data (reporting zeroes)

* **Report Suite Latency**: Occasionally, a report suite can experience [latency](../latency.md) due to a number of factors. Many latency issues are resolved within hours. If you are concerned with a specific report suite, contact Adobe Customer Care with the affected report suite ID.
* **Implementation removal**: Sometimes when an organization makes implementation changes or restructures their site, reimplementing Analytics is overlooked. Work with developers in your organization to reimplement the code on your site.
* **Analytics interface/caching issue**: On rare occasions, a browser's cache contains invalid data that makes all reports return zeros. Clear the browser's cookies and cache to resolve the issue. If clearing your cookies/cache does not work, contact Customer Care with the missing report and date range; they can duplicate the issue and provide additional information.
* **Analytics availability**: Check [status.adobe.com](https://status.adobe.com/products/1173/) for any issues with data collection or processing.

### Potential causes of partially missing data or decreased traffic

* **Implementation changes**: Use the [debugger](/help/implement/validate/debugger.md) to validate that the desired dimensions work.
* **Decreased referring traffic**: If a popular banner ad or hyperlink on another site is removed, it can cause a dramatic decrease in traffic. Trend the [Referring domains](/help/components/dimensions/referring-domain.md) dimension from before and after the drop to research further.
* **Site performance issues**: Incorrect distribution of traffic through load balancers or server issues hosting your site can contribute to a decrease in Analytics reporting. Work with the team within your organization that manages the integrity and health of your site to investigate any potential performance issues.
* **Changes in natural search ranking**: Traffic can potentially decrease if another site ousts your natural search ranking for some of your keywords. This decrease can be especially evident if your site is no longer on the first page of search results. Trend the [Search engines](/help/components/dimensions/search-engine.md) dimension to research further.
* **Changes in PPC advertising**: Changing ad titles and descriptions for existing campaigns can affect your Quality Score. In general, a high Quality Score means that your keyword triggers ads in a higher position and at a lower cost per click. Trend the [Search keywords - paid](/help/components/dimensions/search-keyword.md) dimension to research further.

## Traffic spikes

Traffic spikes are categorized into two sections: near double data and other causes.

### Potential causes of having near or exactly double the expected data

* **Multiple image requests within an implementation**: If your implementation contains more than one [`t()`](/help/implement/vars/functions/t-method.md) method call per page, it effectively doubles all data collected. Use the debugger on your site and watch for multiple image requests to catch duplicates.
* **Duplicate data source files uploaded**: If your organization uses [Data sources](/help/import/data-sources/overview.md), a user in your organization can upload the same file twice to Adobe Analytics. Performing this duplicate upload effectively doubles that data in reporting, causing the traffic spike.

### Other potential causes of increased traffic

* **Spiders or bots**: If you see a large sudden increase in traffic, the first thing to look for is the possibility of a spider or bot. Identifying bots can sometimes be tricky, as each have their own way of executing code on your site. Create a Data Warehouse report using IP as a dimension to see which addresses cause the most traffic. You can then use either [Bot Rules](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) or a VISTA rule to eliminate bot traffic from future reporting.
* **Launched campaigns**: Marketing efforts such as email campaigns or search engine optimization can potentially cause a traffic spike on your site. Trend the [Tracking code](/help/components/dimensions/tracking-code.md) dimension to research further. It can also help to contact your marketing team to ensure that the spike was intentional.
* **Environmental or circumstantial causes**: If a holiday or circumstantial event occurred (a significant event where your site is a known resource, or residual marketing efforts of other organizations), traffic can increase on your site. Troubleshooting the exact cause is difficult, as there are a near unlimited number of circumstantial reasons why traffic can increase. These causes however are some of the most important to determine so your organization can take advantage of them and make business decisions accordingly. Trending the [Page](/help/components/dimensions/page.md) or [Referrer](/help/components/dimensions/referrer.md) dimension is most likely the best place to start in determining the source of the traffic.

If none of the above reasons are potential causes of increased or decreased traffic on your site, contact Adobe Customer Care. They can provide assistance in locating the source of the traffic spike or drop. When creating the incident, instruct the agent on how to recreate a specific report that clearly illustrates the spike or drop.
