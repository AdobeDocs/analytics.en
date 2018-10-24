---
description: Implement Analytics using an HTML image tag (hardcoded image request).
keywords: Analytics Implementation;html image tag;hardcoded image request
seo-description: Implement Analytics using an HTML image tag (hardcoded image request).
seo-title: Implement Analytics using HTML image tags
solution: Analytics
title: Implement Analytics using HTML image tags
topic: Developer and implementation
uuid: b90de9e3-d9ea-4d21-9780-78f3e1e25570
index: y
internal: n
snippet: y
---

# Implement Analytics using HTML image tags

Implement Analytics using an HTML image tag (hardcoded image request).

The browser then requests the image. Data moves with this image request via variables in the query string of the image request. The JavaScript combines browser-level variables with page-level variables for a comprehensive data collection solution. In some cases, a fully server-created image tag is appropriate. The standard elements of a JavaScript-based implementation are listed as follows: 

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> HTML Code </td> 
   <td> This portion consists of JavaScript code that is placed in HTML pages (or templates) that set the value of JavaScript variables. </td> 
  </tr> 
  <tr> 
   <td> JavaScript Library </td> 
   <td> <p>This file contains common code that: </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Queries the browser about various properties, such as JavaScript version, OS version, the size and resolution of monitor being used, and other variables </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Encodes and concatenates all the variables into an image request (&lt;img&gt;) that transports these variables to the data collection servers. It then references a JavaScript library file which is loaded and executed. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> &lt;noscript&gt; tag </td> 
   <td> A simplified version of the image request is placed within a &lt;noscript&gt; tag that executes if the user has disabled JavaScript, or does not have JavaScript capabilities. This part of the implementation is optional and generally applies to approximately 2% of the Internet population. </td> 
  </tr> 
 </tbody> 
</table>

JavaScript can detect browser settings that are not available to a server, such as browser window height/width, monitor resolution, and Netscape plug-ins. By using a server-side method to create an image tag, these variables cannot be captured. The JavaScript sets a random number in the image request to overcome browser and proxy server caching. This allows all page views to be accurately tracked. In certain situations, server-side code has advantages over the JavaScript-based code, including the following:

* JavaScript is very accurate (98-100%). There are times when the utmost accuracy is desired, even in situations where a user quickly clicks to another page before the JavaScript has executed. Creating the image tag server-side increases the accuracy level by several percentage points. 
* For tracking conversion events, such as purchases, where accuracy is very important. 
* This strategy may also be used to fully populate the image request within the <noscript> tag for tracking users without JavaScript, or with JavaScript disabled.

>[!NOTE]
>
>The use of server-generated image tags requires additional time to implement, and is more difficult to debug, deploy, and maintain. Adobe strongly encourages clients to use JavaScript-based data collection on every page where possible. Various reports and features, including visitor click map, download links, exit links, and browser-based variables (browser width/height, etc.) cannot be collected or supported using this implementation method.

