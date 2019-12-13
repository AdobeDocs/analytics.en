---
description: Implement Analytics using an HTML image tag (hardcoded image request).
keywords: Analytics Implementation;html image tag;hardcoded image request
title: Implement Analytics using HTML image tags
topic: Developer and implementation
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
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

> [!NOTE] The use of server-generated image tags requires additional time to implement, and is more difficult to debug, deploy, and maintain. Adobe strongly encourages clients to use JavaScript-based data collection on every page where possible. Various reports and features, including visitor click map, download links, exit links, and browser-based variables (browser width/height, etc.) cannot be collected or supported using this implementation method.

## Implement without JavaScript guidelines

There are additional requirements and configurations for implementing Analytics without JavaScript.

You can view sample code to further understand the implementation. The following information outlines the additional requirements and configurations: 

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Case-Sensitive**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](/help/implement/js-implementation/data-collection/query-parameters.md).

**Encode Query Parameters**

The values for each of the query string parameters must be URL encoded. URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with `%`. For example, a space character is converted into `%20`.

The JavaScript version of this function is called escape (and to decode, unescape). Microsoft IIS Version 5.0 also includes an Escape and Unescape function for encoding query strings. Other Web server scripting languages also provide encoding/decoding utilities.

**Maximum Variable Length**

Each variable has a maximum length. This length is specified for each variable in [Analytics Variables](/help/implement/js-implementation/c-variables/sc-variables.md). Exceeding the maximum length for a variable causes the value of this variable to be truncated for storage and display in Analytics.

**Invalid Characters**

Characters with character codes above decimal 128 are invalid, as are not-printing character codes under 128. HTML formatting ("&lt;h1&gt;") is also invalid, as are trademark, registered trademark, and copyright symbols.

**Secure (&lt;https:&gt; vs. Non-Secure (&lt;http:&gt;) Image Requests**

On pages that are accessed via https (secure protocol), the URL portion of the image request changes to accommodate a different set of data collection servers.

The following information illustrates the different URLs used for secure and non-secure image requests.

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe uses several data centers, and it is necessary to implement the correct URL your organization has been assigned. Any code downloaded out of Admin Console within your company account has the correct data center supplied automatically. Code provided from external sources may need to be corrected in order to point to the correct data center.
* For clients who use multiple report suites, they should be listed only in the directory section, and not the domain section of the URL, as shown below.
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe uses several data centers, and it is necessary to implement the correct URL to which your organization has been assigned.

**URL and Referring URL**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

If pageName is not being used, it is imperative that the Current URL field is uniquely populated. If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. At a minimum, the URL is a required field in order to process the record.

**Effects of Caching**

HTML and other Web pages can be cached by browsers or servers that are between the visitor and the website that is serving the content. Caching prevents an accurate count of page views and other events unless a "cache-busting" technique is employed.

Adobe's standard JavaScript includes a dynamic method of changing the image request to avoid page and image caching, allowing an accurate count of page views.

However, in creating a server-side image request, this randomization does not occur. Page reloads and cached pages (either in the browser's cache or in a proxy server) are not counted in certain cases when using server-side image requests.

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) are also not cached.

The examples below also illustrate a minimal JavaScript solution that primarily assembles the image request server-side, and tacks on a random number in the browser. This method overcomes the caching that would otherwise be encountered on static HTML pages accessed via the https: protocol.

**nameSpace Variable**

The nameSpace query string parameter is required for non-JavaScript implementations.

Example: ns=nameSpace

Contact your Adobe Consultant or Account Manager to obtain your organization's nameSpace value.
