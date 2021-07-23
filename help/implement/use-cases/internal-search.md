---
title: Capture internal search terms
description: Use a custom variable to capture internal search terms.
---

# Capture internal search terms

Internal search reporting is integral to many organizations, and is not an out-of-the-box dimension with Adobe Analytics. However, with minimal implementation efforts, internal search term reporting can easily be captured.

## Prerequisites

[Validate a development implementation and publish to production](../launch/validate-publish-prod.md): This page assumes that you have a basic working implementation, and see an Adobe Analytics image requests in the Adobe debugger.

## Create an eVar to accommodate internal search

Follow [Conversion variables admin](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) to create a new eVar dedicated to internal search. Give the eVar an easily recognizable name (such as "Internal search term"), and record the new eVar in your organization's [Solution design document](../prepare/solution-design.md).

## Determine internal search keyword

Most internal searches use query strings to pass keyword data between pages. Use your site's internal search and note the URL on the search results page:

`https://example.com/search.html?q=kittens`

If your site's internal search doesn't use the URL, look for the search term in other locations, such as a data layer or cookie. Work with your site development team if you are not sure where to find internal search term.

## Assign the query string parameter to a data element

Follow [Map data layer objects to data elements](../launch/layer-to-elements.md). When selecting the **[!UICONTROL Data Element Type]**, select **[!UICONTROL Query string parameter]** instead of **[!UICONTROL JavaScript Variable]**. Put the desired query string parameter (typically `q`) in the text field.

## Map the data element to the eVar

Follow [Map data elements to Analytics variables](../launch/elements-to-variable.md). Make sure that you select the same eVar that you created in Report suite settings.

## Start deploying tags

Follow [Deploy an Analytics implementation to a development environment](../launch/deploy-dev.md). Once you have confirmed it is working in your dev environment, you can [Validate a development implementation and publish to production](../launch/validate-publish-prod.md).

## Reporting in Workspace

Give your implementation some time to collect data, then you can start using the dimension in Analysis Workspace.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. If you aren't automatically logged in to Adobe Analytics, click the 9-grid icon in the top right, and select **[!UICONTROL Analytics]**.
3. Click the **[!UICONTROL Workspace]** tab, and create a new project.
4. Locate the name of the eVar you created under Dimensions, and drag it to the workspace canvas.
