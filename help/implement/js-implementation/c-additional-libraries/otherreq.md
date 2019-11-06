---
description: There are additional requirements and configurations for implementing Analytics without JavaScript.
keywords: Analytics Implementation;case sensitive;encode query parameters;invalid characters;secure image requests;maximum variable length;referring;url;caching;namespace
seo-description: There are additional requirements and configurations for implementing Analytics without JavaScript.
seo-title: Implement without JavaScript guidelines
solution: Analytics
title: Implement without JavaScript guidelines
topic: Developer and implementation
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
---

# Implement without JavaScript guidelines

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
