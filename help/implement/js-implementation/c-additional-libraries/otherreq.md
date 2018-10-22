---
description: There are additional requirements and configurations for implementing Analytics without JavaScript.
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
seo-description: There are additional requirements and configurations for implementing Analytics without JavaScript.
seo-title: Implement without JavaScript guidelines
solution: Analytics
title: Implement without JavaScript guidelines
topic: Developer and implementation
uuid: e6890eaf-5e29-41bb-bdce-2f07c63a5c31
index: y
internal: n
snippet: y
---

# Implement without JavaScript guidelines

There are additional requirements and configurations for implementing Analytics without JavaScript.

You can view sample code to further understand the implementation. The following table outlines the additional requirements and configurations: 

<table id="table_18913E19D61143A28AB170D1492B8A0C"> 
 <thead> 
  <tr> 
   <th class="entry"> Requirement </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Case-Sensitive </td> 
   <td> The parameter names (<span class="varname"> pageName</span>, <span class="varname"> purchaseID</span>, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in <a href="../../js-implementation/data-collection/query-parameters.md#concept_2F280ECF4205465FA9B5D773046C1A15" format="dita" scope="local"> Query Parameters</a>. </td> 
  </tr> 
  <tr> 
   <td> Encode Query Parameters </td> 
   <td> <p> The values for each of the query string parameters must be URL encoded. URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with %. For example, a space character is converted into %20. </p> <p>The JavaScript version of this function is called escape (and to decode, unescape). Microsoft IIS Version 5.0 also includes an Escape and Unescape function for encoding query strings. Other Web server scripting languages also provide encoding/decoding utilities. </p> </td> 
  </tr> 
  <tr> 
   <td> Maximum Variable Length </td> 
   <td> Each variable has a maximum length. This length is specified for each variable in <a href="../../js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB" format="dita" scope="local"> Analytics Variables</a>. Exceeding the maximum length for a variable causes the value of this variable to be truncated for storage and display in <span class="keyword"> Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td> Invalid Characters </td> 
   <td> Characters with character codes above decimal 128 are invalid, as are not-printing character codes under 128. HTML formatting ("&lt;h1&gt;") is also invalid, as are trademark, registered trademark, and copyright symbols. </td> 
  </tr> 
  <tr> 
   <td> Secure (https:&gt; vs. Non-Secure (http:) Image Requests </td> 
   <td> <p>On pages that are accessed via https (secure protocol), the URL portion of the image request changes to accommodate a different set of data collection servers. </p> <p>The following table illustrates the different URLs used for secure and non-secure image requests. </p> <p>  </p>
    <table id="table_4DD27C32DFCD42A392D1A2577CB34ED7">  
    </table> <p> The * in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe uses several data centers, and it is necessary to implement the correct URL your organization has been assigned. Any code downloaded out of Admin Console within your company account has the correct data center supplied automatically. Code provided from external sources may need to be corrected in order to point to the correct data center. </p> <p> For clients who use multiple report suites, they should be listed only in the directory section, and not the domain section of the URL, as shown below. </p> <p>  </p>
    <table id="table_8B770D26088F4D83BDDBF19C03BB13F9">  
    </table> <p> The * in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe uses several data centers, and it is necessary to implement the correct URL to which your organization has been assigned. </p> </td> 
  </tr> 
  <tr> 
   <td> URL and Referring URL </td> 
   <td> The URL and Referring URL may be populated from the server in the <span class="wintitle"> g=</span> and <span class="wintitle"> r=</span> variables. Use the <span class="wintitle"> Request ServerVariables</span> (HTTP_REFERRER) or <span class="wintitle"> Request ServerVariables</span> (URL) (IIS/ASP), or the appropriate variable for your server/scripting technology. The referring URL (<span class="wintitle"> r=</span>) is extremely important for tracking referring URLs, domains, search engines, and search terms. <p> If <span class="varname"> pageName</span> is not being used, it is imperative that the <span class="wintitle"> Current URL</span> field is uniquely populated. If neither <span class="varname"> pageName</span> nor <span class="wintitle"> Current URL (g=)</span> is populated, the record is invalid and is not processed. At a minimum, the URL is a required field in order to process the record. </p> </td> 
  </tr> 
  <tr> 
   <td> Effects of Caching </td> 
   <td> <p>HTML and other Web pages can be cached by browsers or servers that are between the visitor and the website that is serving the content. Caching prevents an accurate count of page views and other events unless a "cache-busting' technique is employed. </p> <p> Adobe's standard JavaScript includes a dynamic method of changing the image request to avoid page and image caching, allowing an accurate count of page views. </p> <p>However, in creating a server-side image request, this randomization does not occur. Page reloads and cached pages (either in the browser's cache or in a proxy server) are not counted in certain cases when using server-side image requests. </p> <p>SSL (https:) pages are not, by definition, ever cached so this warning applies only to non-secure (http:) pages. Additionally, pages with parameters (<span class="filepath"> http://www.samplesite.com/page.asp?parameter=1</span>) or certain file extensions (<span class="filepath"> .asp</span>, <span class="filepath"> .jsp</span>, etc.) are also not cached. </p> <p> The examples below also illustrate a minimal JavaScript solution that primarily assembles the image request server-side, and tacks on a random number in the browser. This method overcomes the caching that would otherwise be encountered on static HTML pages accessed via the http: protocol. </p> </td> 
  </tr> 
  <tr> 
   <td> nameSpace Variable </td> 
   <td> <p>The <span class="wintitle"> nameSpace</span> query string parameter is required for non-JavaScript implementations. </p> <p>Example: ns=nameSpace </p> <p> Contact your Adobe Consultant or Account Manager to obtain your organization's <span class="wintitle"> nameSpace</span> value. </p> </td> 
  </tr> 
 </tbody> 
</table>

