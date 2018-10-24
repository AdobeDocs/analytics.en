---
description: A common usage of content hierarchies is to show the different paths visitors have taken from a certain page, level, and so forth.
keywords: Analytics Implementation;content hierachies;hier
seo-description: A common usage of content hierarchies is to show the different paths visitors have taken from a certain page, level, and so forth.
seo-title: Counting content hierarchies
solution: Analytics
title: Counting content hierarchies
topic: Developer and implementation
uuid: 4b0073fa-ab49-455c-89e7-59f8017253ee
index: y
internal: n
snippet: y
---

# Counting content hierarchies

A common usage of content hierarchies is to show the different paths visitors have taken from a certain page, level, and so forth.

*** How should I track my [!UICONTROL content hierarchy]?* **

You must first understand the reporting requirements for tracking [!UICONTROL content hierarchies]. If the requirements for tracking the hierarchy are very detailed, often times the hierarchy ( *`hier`*) variable is recommended. Hierarchies usually require a strict, predefined taxonomy where the same child node rarely lives under multiple parent nodes. Consider the following example:

[!UICONTROL Global Hierarchy]

All Sites > Regions > Countries > Language > Category

In this example, the hierarchy could begin to break down at the language level. If a requirement is to report on overall "English" traffic, you can run into the problem where English appears under USA, England, Australia, and so forth. Hierarchies allow you to only drill down. In order to slice horizontally across multiple hierarchies, the best practice is to use a [!UICONTROL custom traffic variable] (prop).

If you want to provide users with the ability to drill down through the site (similar to how users would browse the site) and report on [!UICONTROL Unique Visitors] at each level of the hierarchy, the hierarchy variable is recommended.

There are occasions when using both props and the *`hier`* variable makes sense. The following is a supported prop for each variable type: 

<table id="table_E960D100DA0F433A94A4B246D6EF0D0A"> 
 <thead> 
  <tr> 
   <th class="entry"> </th> 
   <th class="entry"> Props </th> 
   <th class="entry"> Hierarchy </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Correlations </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_2A70A61A78024204B6CEE4FFF9A0851E" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Pathing </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_EE5ED36AC75F4D648F54858D796F82BD" /> </p> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Page View </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_5BB82776D41642E78C2ECFD71DD33164" /> </p> </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_18F34EE8957946AF9D6C2C9B492CEDB7" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Unique Visitors </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_A475267547B94DB4A1EEFD903B2CA1EB" /> </p> </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_1E9E302D999146128CDBCE13E52BC38C" /> </p> </td> 
  </tr> 
  <tr> 
   <td> Classifications </td> 
   <td> <p style="text-align: center;"><img href="assets/check-mark.png" id="image_FC5FEFE7BA8C4475BA4F31D57302BE6B" /> </p> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

