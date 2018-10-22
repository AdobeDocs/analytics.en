---
description: Example containing a sample of server calls sent in a common customer interaction.
keywords: Analytics Implementation
seo-description: Example containing a sample of server calls sent in a common customer interaction.
seo-title: Example visit
solution: Analytics
subtopic: Visitors
title: Example visit
topic: Developer and implementation
uuid: a4fd2fd8-6337-453f-99c5-37b89ce29c1a
index: y
internal: n
snippet: y
---

# Example visit

Example containing a sample of server calls sent in a common customer interaction.

<table id="table_BD711278026C4F729119F1FDF4945087"> 
 <thead> 
  <tr> 
   <th class="entry"> Server Call </th> 
   <th class="entry"> Action </th> 
   <th class="entry"> Visitor ID Cookie </th> 
   <th class="entry"> Visitor ID Variable </th> 
   <th class="entry"> Effective Visitor ID </th> 
   <th class="entry"> Visit Page Number </th> 
   <th class="entry"> Visit Number </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 1 </td> 
   <td> A visitor clicks a link in a marketing email and visits your site from home computer. This visitor has visited your site 7 other times in the past. </td> 
   <td> 1 </td> 
   <td> - </td> 
   <td> 1 </td> 
   <td> 1 </td> 
   <td> 8 </td> 
  </tr> 
  <tr> 
   <td> 2-8 </td> 
   <td> Visits 7 additional pages on your site. </td> 
   <td> 1 </td> 
   <td> - </td> 
   <td> 1 </td> 
   <td> 2-8 </td> 
   <td> 8 </td> 
  </tr> 
  <tr> 
   <td> 9 </td> 
   <td> Authenticates on home computer. </td> 
   <td> 1 </td> 
   <td> CID1 </td> 
   <td> CID1 </td> 
   <td> 9* <p>* This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1. </p> </td> 
   <td> 8 </td> 
  </tr> 
  <tr> 
   <td> 10 </td> 
   <td> Visits 1 additional page. </td> 
   <td> 1 </td> 
   <td> CID1 </td> 
   <td> CID1 </td> 
   <td> 10 </td> 
   <td> 8 </td> 
  </tr> 
  <tr> 
   <td> 11 </td> 
   <td> Opens site from laptop at office. This visitor has not visited your site before using this device. </td> 
   <td> 2 </td> 
   <td> - </td> 
   <td> 2 </td> 
   <td> 1 </td> 
   <td> 1 </td> 
  </tr> 
  <tr> 
   <td> 12 </td> 
   <td> Authenticates on laptop. </td> 
   <td> 2 </td> 
   <td> CID1 </td> 
   <td> CID1 </td> 
   <td> 1 </td> 
   <td> 9 </td> 
  </tr> 
  <tr> 
   <td> 13 </td> 
   <td> Views 1 additional page. </td> 
   <td> 2 </td> 
   <td> CID1 </td> 
   <td> CID1 </td> 
   <td> 2 </td> 
   <td> 9 </td> 
  </tr> 
 </tbody> 
</table>

