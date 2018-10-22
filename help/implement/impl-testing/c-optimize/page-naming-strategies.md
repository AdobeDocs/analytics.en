---
description: The pageName variable should be populated with an easy-to-read, intuitive, page identifier.
keywords: Analytics Implementation
seo-description: The pageName variable should be populated with an easy-to-read, intuitive, page identifier.
seo-title: Page naming strategies
solution: Analytics
title: Page naming strategies
topic: Developer and implementation
uuid: 70dd9f28-4ce0-452a-9827-ffb308631318
index: y
internal: n
snippet: y
---

# Page naming strategies

The pageName variable should be populated with an easy-to-read, intuitive, page identifier.

 You can determine the best way of populating the *`pageName`* variable by looking at the structure of your website. The methods listed below outline various ways of populating the *`pageName`* variable.

While the *`pageName`* variable is central to identifying user behavior, Adobe recommends using multiple variables to indicate page information. The best page naming strategies use a different variable for each level of hierarchy within your site, as shown below:

* The *`channel`* variable can be used to indicate the site section. 
* The *`pageName`* variable can be used to show content type. 
* A [!UICONTROL custom insight] variable (prop1) can be used for detailed content.

Levels of detail vary, depending on property, as shown below: 

|  Variable  | Level of Detail  | Example  |
|---|---|---|
|  Channel  | General Section  | Electronics  |
|  Prop1  | Sub Section  | Sports : Local Sports  |
|  PageName  | General Content Description  | Loans : Home Mortgage : Rate Comparison  |
|  Prop2  | Detailed Content Description  | Electronics : Notebook PC : Detailed Specs : IBM Thinkpad T20  |

The more layered your site, the more variables should be used to identify page content. Companies also find value in allowing for overlap between variables. For example, a more detailed variable may contain information not only about the product being viewed, but also about the site section and sub-section. This is particularly helpful when a product or article appears in more than one section of the site.

The following page naming strategies describe how to populate the *`pageName`* variable. While it is tempting to choose the page naming strategy that is easiest to implement, the page naming strategy largely determines the usability of all [!UICONTROL Path] and [!UICONTROL Page] reports. Use good judgment when deciding how pages are named.

## Unique Name for Each Page {#section_24704CA39E2F4C00ACEAFF39CA0A921B}

The most valuable method of naming pages is to give each page a unique identifier that is easily understood by all [!DNL Analytics] users in your organization. Examples of page names include Home Page, Electronics Department Home, and Sports : Local Sports : High School.

Most [!DNL Analytics] users find that hierarchical page names are useful in both identifying where the page is found on the site and its purpose. The following table shows some sample page names for various industries: 

|  Conversion  | Media  | Finance  |
|---|---|---|
|  Home Page  | Home Page  | Home Page  |
|  Electronics  | Technology  | Home Loans  |
|  Electronics : Notebook PCs  | Technology : New Gadgets  | Home Loans : Rate Compare  |
|  Electronics : Notebook PCs : Product Page  | Technology : New Gadgets : Article Page  | Home Loans : Rate Compare : 10 Year Fixed  |

## File Path (Not the Full URL) {#section_37FDCDA00DA84B3D9B8AB4290555FF34}

For some sites, the file path is clear and easily read. Any business user can read a URL and determine the page to which the file path refers. If this is the case for your site, you can use a server-side variable to populate the path to the file into the *`pageName`* variable, as shown below:

```js
s.pageName="<%= file_path %>"
```

Adobe does not recommend leaving the *`pageName`* blank, (which results in using the full URL of the page) even though you may be tempted to do so. The following side-effects are caused by leaving the *`pageName`* variable blank and using the *`pageURL`* as the page identifier.

* The domain and path of a page may not always be displayed identically. For example, the following four URLs return a single page:

    * [!DNL http://www.mysite.com/index.jsp] 
    * [!DNL http://www.mysite.com] 
    * [!DNL http://mysite.com/index.jsp] 
    * [!DNL http://mysite.com/]

  If the *`pageName`* is left blank, each of these page names would occupy a separate entry in reports. 

* Some pages (such as forms) post to themselves, thereby erasing any distinction between the original form and the resulting output. 
* When your page is translated into another language by search engines or other online tools, the URL of the page is the URL of the search engine (not the URL of your site).

## HTML (document.title) {#section_B99B8F66B0E2410FA7BFE44E6851EB3F}

If you have invested time into making your HTML titles readable and intuitive, you might consider using the same title as the value in the *`pageName`* variable. Adobe recommends using a server-side variable to populate the *`pageName`* rather than using JavaScript's [!DNL document.title]. Some browsers interpret the HTML title differently than others, which may cause [!DNL Analytics] to receive different page names from different browsers.

The best practice for using the HTML title is to copy the existing titles for each page into a separate variable or content management element. When you decide to make changes to the HTML title for search engine optimization or other purposes, the [!DNL Analytics] page names are not affected. If a page name changes in [!DNL Analytics], it becomes a new page and is not connected with the old page name, regardless of the associated URL. 
