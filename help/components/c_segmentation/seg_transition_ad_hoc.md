---
description: If you are used to working with the Segment Builder in Ad Hoc Analysis, this FAQ explains what happens to existing segments and folders and what actions you need to take.
keywords: segmentation;segments
seo-description: If you are used to working with the Segment Builder in Ad Hoc Analysis, this FAQ explains what happens to existing segments and folders and what actions you need to take.
seo-title: Transition Guide for Ad Hoc Analysis
solution: Analytics
title: Transition Guide for Ad Hoc Analysis
topic: Segments
uuid: b13e75a8-f657-47d5-9a8b-09154c10d9f0
index: y
internal: n
snippet: y
---

# Transition Guide for Ad Hoc Analysis

If you are used to working with the Segment Builder in Ad Hoc Analysis, this FAQ explains what happens to existing segments and folders and what actions you need to take.

## Features {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* Segments are universal to all report suites. Previously, segments were report-suite specific. 
* Ad Hoc Analysis includes updates to the Segment Builder and a complete update of the Segment Manager. 
* You can now tag segments to organize and search later instead of using folders. Previously, you used folders in [!DNL Ad Hoc Analysis] to organize your segments.

See [ad hoc analysis release notes](http://marketing.adobe.com/resources/help/en_US/dsc/?f=c_release_notes_dsc) for additional information.

## What happened to my existing segments? {#section_76CF47142D1A4FB6A0718AD9073049FE}

Your existing segments will continue to work as they did before. Any reports that have these segments applied will continue to work correctly.

Most former pre-defined and suite segments will be migrated over as segment templates into the segment builder. Segment templates are used to quickly build custom segments with common audiences. Segment templates can't be applied to a report directly, but they can be easily saved to a custom segment.

Segment templates are marked with a special icon in Segment Builder.

## What happened to my existing segment folders? {#section_FB04DCF775694E69B761DCA53F301C30}

Instead of ad hoc analysis folders, the Segment Manager uses tags. Your folder names are automatically converted to tags and those tags are applied to the respective segments.

## What happened to scheduled reports that have segments applied? {#section_81D1B215533C46E99E17BAE7A3376FDF}

Scheduled reports continue to run properly with the segments that you defined.

When you delete a segment, scheduled reports and dashboards that have this segment applied continue to work normally, i.e. the segment or dashboard continues to use the deleted segment.

## What is a Hit Container? Is it different from a Page View Container? {#section_65BBE60A836C4001938830DDA15DC256}

The Page View container was renamed to the Hit container to indicate that this container segments all types of data and not just page views. For example, link tracking calls, and trackAction calls from the mobile SDKs are all included or excluded by the hit container.

Note that there wasn't a change to the way this container functions, it was simply renamed.

## What rights and privileges do I need to use, create, and manage segments? {#section_648DFA3A882146C485A84ED014EEC707}

All users can create and edit personal segments. These segments can be shared directly with any other Analytics user. Ad Hoc Analysis users can see the segments each created and those shared directly with the user.

In the Unified Segmentation web console, Admins can edit any segment, and share segments with groups and with everyone in the organization.

## Can I see all segments in my company? {#section_AC2D328C7410419E80C7C17971CD95B3}

All ad hoc analytics segments that you own and segments that are specifically shared with you are displayed.

## Can I manage all Analytics segments in the Segment Manager? {#section_AF5EDD72C74A4739BD40C4AF125CE489}

Ad hoc analysis only displays segments built by you or segments that have been shared specifically with you. For ad hoc analysis only, you can use the Segment Manager (Organize Segments) to manage ad hoc analysis segments. Use the Segment Manager in Unified Segmentation to manage all Analytics' segments.

## What should I do with duplicate segments that have the same name but may have different definitions? {#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

Now that segments work in multiple report suites, you might find that you have multiple segments with the same name. We recommend that you either

* Rename segments that have the same name, but different definitions, or 
* Delete segments that are no longer necessary.

## How does Adobe recommend that I clean up segments? {#section_3AC2D265F9084557A24C6FB39DC6EE49}

* Tag all segments with legacy tag. 
* Review the segments that you have. 
* Add them to the segment library where applicable. 
* Approve segments that are canonical.

## Why can't I delete this segment? {#section_0FEB6711031A4ABCA915CDA745ECF38D}

If the segment was published to the Experience Cloud, you cannot delete it or edit it. However, you can copy it and edit the copied version.

## More on what happens to your existing segments {#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Segment Category </th> 
   <th colname="col2" class="entry"> What happens to these segments? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Favorites Segments in Ad Hoc Analysis </td> 
   <td colname="col2">These Ad Hoc Analysis segments are displayed as regular segments in Adobe Analytics. <p>They should not be confused with the Favorites feature in the Segment Manager that lets you mark segments as favorites. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Pre-Configured Segments in Ad Hoc Analysis: 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">Single Page Visits </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">Visits from Mobile Devices </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">Visits from Natural Search </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">Visits from Paid Search </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">Visits with Visitor ID Cookie </li> 
    </ul> </td> 
   <td colname="col2"> <p>These segments will be migrated over as segment templates into the segment builder. </p> <p>Existing reports that have these segments applied will continue to work correctly. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud (Suite) segments: 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">Non-Purchasers </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">Purchasers </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">First Time Visits </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">Visits from Social Sites </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">Visits of More than 10 Minutes* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">Visits with 5+ Previous Visits* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">Visits from Facebook* </li> 
    </ul> </td> 
   <td colname="col2"> <p> Most of these segments (except the ones marked with an asterisk *) will be migrated over as segment templates into the segment builder. Additionally, several new segment templates have been added. </p> <p>Existing reports that have these segments applied will continue to work correctly. </p> </td> 
  </tr> 
 </tbody> 
</table>

