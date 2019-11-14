---
description: There are several types of variables available in the Experience Cloud. The two most popular types, Props and eVars, allow your organization to report on custom dimensions to your site that standard out-of-the-box reports do not offer.
keywords: Analytics Implementation;prop;evar;props vs evars;naming convention;traffic variables;persistence;success event;pathing
solution: Analytics
title: Comparing Props and eVars
topic: Developer and implementation
uuid: 0f02760f-ff69-481c-a817-799f02dafe8e
---

# Comparing Props and eVars

There are several types of variables available in the Experience Cloud. The two most popular types, Props and eVars, allow your organization to report on custom dimensions to your site that standard out-of-the-box reports do not offer.

When determining which variables are assigned where, it is important to understand the differences between Prop and eVar functionality. Understanding these differences allows your organization to decide which type of variable is best to use.

**Props vs eVars**

The following are the main differences between props and eVars:

* **Naming convention**: Props are considered traffic variables, meaning they are used to report on popularity of various dimensions of your site. eVars are considered conversion variables. They are used to determine which dimensions of your site contribute the most to success events.
* **Persistence**: Props do not persist beyond the image request they were fired on. They cannot be associated with other variables that are not in the same image request. eVars, however, are persistent. A back-end variable is used to preserve the value originally fired so it can associate itself with success events later on.
* **Success events**: Success events, also known as conversion events, are metrics that measure the number of times a visitor reaches a goal. This event can be anything from purchasing something on your site, to subscribing to a newsletter. eVars are designed to report on conversion events, to show you which values are most successful in influencing visitors to reach your goals. Traffic variables do not have this same functionality. However, you can view participation metrics if you configure your report suite correctly.
* **Pathing**: Props can use pathing, which allows your organization to see a given path a user took within the context of the variable being viewed. An Adobe representative can enable pathing, if requested. eVars cannot use pathing.
* **Potentially available metrics**: The metrics available between props and eVars vary widely based on the variable's settings and data platform/version. The following list illustrates what can be enabled, not what is enabled by default. If you want a specific metric in reporting but do not see it, have one of your organization's supported users contact Customer Care.  

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Metric </p> </th> 
   <th colname="col2" class="entry"> <p>Props </p> <p>(Traffic Variables) </p> </th> 
   <th colname="col3" class="entry"> <p>eVars </p> <p>(Conversion Variables) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Average Page Depth </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Average Time Spent </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bounce Rate </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bounces </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calculated Metrics </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Conversion Events </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Entries </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exits </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Instances </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Page Views </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Participation Metrics </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Purchase Metrics </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reloads </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Shopping Cart Metrics </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Access </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Total Time Spent </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unique Visitors </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Visits </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **Breakdowns**: Props use correlations, which display page views for other traffic variables fired in the same image request. eVars use subrelations, which provide a breakdown on other conversion variables in relation to success events.

## Exclusive advantages to Props or eVars {#section_B384031AB8674065BA5187B0A3A3DAB9}

With the release of version 15, the capabilities between Props and eVars are much less distinct. eVars have recently been updated to include capabilities such as visits/unique visitors with minimal processing load, as well as pathing metrics.

Props hold a couple advantages of eVars, some of which can be circumvented:

* Prop data is collected and available in reporting almost instantly. eVars can take upwards of 30 minutes to appear in report suite data.
* All Props can have flowchart-like reports enabled, which let you see the path visitors take to your site. These pathing flow reports are available for both Props and eVars in [!UICONTROL Ad Hoc Analysis].
* Props can be correlated multiple levels, where eVars can only be subrelated once. This limitation can be mitigated by using segmentation, giving identical data as correlations.
* Participation metrics allow you to see what prop values participated before a success event.

eVars on the other hand hold several advantages over the limited nature of Props:

* eVars can use success events as metrics. Props cannot.
* eVar expiration can be customized, including having an expiration of every hit (no persistent values whatsoever). Props don't persist in any way.

Pathing metrics, such as Total Time Spent, Entries, and Exits, were originally not available for eVars. However, recent updates have made these metrics available, increasing the value of eVars.

## Which to Use {#section_022D016A4EEB45179A15BFF044A261A4}

**Props:** If latency is the largest concern, and you intend to only measure traffic (not success events) with this dimension.

**eVars:** If data breakdowns and relationships are the largest concerns.

>[!TIP]
>
>If you don't want an eVar to persist, you can change its expiration to 'hit' so it doesn't keep any data beyond the hit.

