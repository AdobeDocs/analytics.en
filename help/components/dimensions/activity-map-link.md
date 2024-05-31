---
description: 
title: Activity Map Link
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Dimensions
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
---
# Activity Map Link

The 'Activity Map Link' dimension displays the most popular links that were clicked. You can use this dimension to directly compare which links on your site are used the most.

## Populate this dimension with data

This dimension retrieves data from the [Context data variable](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link`. If your implementation uses [Activity Map](/help/analyze/activity-map/overview.md), this context data variable automatically collects data when links are clicked.

For a given link that was clicked, Activity Map searches for the following (in order):

* The `s_objectID` variable
* The link's inner text
* The `alt` attribute for images
* The `title` attribute
* The `src` attribute for images
* The `action` attribute for forms

If the clicked element contains none of the above criteria, Activity Map does not collect data for that click.

## Dimension items

Dimension values most commonly include the link text that visitors click. Your organization's site structure and implementation determines the exact values collected.


<!--

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) or by excluding ActivityMap link collection with s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions. For more information on how Activity Map may be collecting PII data, go [here](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map bases its link tracking on these two IDs:

* Primary ID: this is the recognizable parameter of the link.
* Link Region: this is a secondary parameter that allows users to specify a string that is representative of the overall link area in the page or region. This parameter can be automatically generated if it is not provided by the user.

## Primary ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

If the HTML has an s_objectid, then the primary ID is defaulted to the s_objectid. Otherwise, the following parameters are used as primary ID (in this order of priority):

* Innertext 
* Alttext 
* Title 
* Src 
* Action

## Using InnerText versus using Link Action (URL) {#section_70C3573E22274522A8CC035BF18EC468}

Link action is the action taken by the web page when the link is clicked - usually the URL that is visited after clicking the link. Some of the issues you might run into when using Link Action are:

* having two or more distinct links with the same ID 
* readability of the link 
* one link with multiple actions (depending on the device where you are viewing the link)

As a result, we use InnerText with these benefits over using Link Action (URL):

* It is a good representation of the Link identity. Primary ID duplication is significantly reduced as it is not common to have multiple links with the same text.
* It ensures consistency of the Primary ID across devices and browser types.
* It is not affected by a link repositioning on the page.
* It improves readability, so users can start analyzing Link tracking reports outside Activity Map. -->