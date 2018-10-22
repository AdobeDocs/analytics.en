---
description: Conditions determine when an event-based rule is triggered.
keywords: Dynamic Tag Management;rule;create rule;new rule;event-based rule;delay link activation;apply event handler directly to element;bubbling;event bubbling
seo-description: Conditions determine when an event-based rule is triggered.
seo-title: Create conditions for event-based rules
solution: Marketing Cloud,Analytics,Target,Dynamic Tag Management
title: Create conditions for event-based rules
uuid: fc34b511-dc6d-4066-9350-d1d42419d680
index: y
internal: n
snippet: y
---

# Create conditions for event-based rules

Conditions determine when an event-based rule is triggered.

1. Select the type of interaction you want to track, such as mouse clicks, or submitting a form.

   ![](assets/condition-event-based.png)

   For more information, see [Event Types](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html) in the Adobe Tag Management Product Documentation. 

1. Enable the following options as necessary:

<table id="table_022B9DA4224F47778F10B9772E2A295F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Delay Link Activation </p> </td> 
   <td colname="col2"> <p>Enable if the event activates a link and you want the link to delay until the event has time to fire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apply event handler directly to element </p> </td> 
   <td colname="col2"> <p>Applies the event handler to the specific element that is targeted. This setting is tied to the bubbling and layering concept in a browser. </p> </td> 
  </tr> 
 </tbody> 
</table>

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. An event like a click can potentially bubble up to `<body>`. It is important to understand where the event is actually bound, and target it specifically to make sure that the rule fires correctly.

   *Bubbling* means that the event is first captured and handled by the inner most element and then propagated to outer elements. 

1. Indicate the name of the tag you want to track, and additional properties the tag has that you want to match.

   ![](assets/condition-event-based2.png)

   See [Using the CSS Selector](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html) in the Dynamic Tag Management Product Documentation for information about finding the correct element tag. 

1. Select and set up any additional criteria or condition types you wish to bind to the rule.

   ![](assets/condition-event-based3.png)

1. Indicate your preference regarding event bubbling.

   Event bubbling is one way of event propagation in HTML DOM.

    <table id="choicetable_2373DBD90E6E467C85D2469FB762AB3E"> 
 <thead class="chhead sthead"> 
  <th class="choptionhd"> If you...</th> 
  <th class="chdeschd"> Check this option</th> 
 </thead> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Want related interactions on child elements of the rule selector you identified to fire the rule.</strong></td> 
  <td class="chdesc stentry"> <p>Allow events on child elements to bubble. </p></td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Want to prevent bubbling when the child element already triggers its own event.</strong></td> 
  <td class="chdesc stentry"> <p>Do not allow if child element already triggers event. </p></td> 
 </tr> 
 <tr class="chrow strow"> 
  <td class="choption"><strong>Don't want the events of the rule selector you identified to go beyond the element itself in the event hierarchy.</strong></td> 
  <td class="chdesc stentry"> <p>Do not allow events to bubble upwards to parents. </p></td> 
 </tr> 
</table>    
    
