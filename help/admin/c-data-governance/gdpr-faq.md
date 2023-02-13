---
description: Adobe Analytics data governance FAQ
title: Frequently asked questions for data governance
feature: Data Governance
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
---
# Frequently asked questions

+++ **How does Adobe Analytics support access and delete requests for end users (Data Subjects) validated by customers (Data Controllers)?**

When various Data Privacy rules (GDPR, CCPA) take effect, Adobe Analytics will support processing verified requests submitted by Data Controllers to the Experience Cloud Data Privacy API to enable a more automated process. Adobe's Data Privacy API is designed to help process individual rights requests (e.g., access and delete requests) for our customers' data stored across Adobe Experience Cloud solutions. It is flexible and scales according to the number of data access and delete requests your company receives from Data Subjects. 

Also, the Privacy Service API allows the customer to check the status on how the data access and delete requests that are being fulfilled. For more details see [Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) documentation.

+++

+++ **Who is responsible for receiving, accepting, and fulfilling Data Privacy requests from end users?**

The Data Controller has the sole responsibility for receiving and accepting requests. The Data Controller validates the Data Subject's identity and then fulfills the request. Part of this repsobsibility may involve contacting Adobe with Data Subjects' IDs that may be associated with data stored in Adobe Analytics. 

As the Data Processor, Adobe must provide reasonable assistance to the Controller to process verified requests within an acceptable amount of time.

+++

+++ **How will Adobe Customers (Data Controllers) find out which Data Privacy requests map to which IDs in Adobe Analytics for Data Privacy processing?**

The Data Controllers determine how to resolve identity for requests from the Data Subjects. Consider deploying  Adobe's Data Privacy ID Retrieval Tag. Your development teams save time by using our Data Privacy ID retrieval tag to capture user IDs (cookie IDs). They can then use our Data Privacy API to send those user IDs to the relevant solutions in the Adobe Experience Cloud for Data Privacy request processing. The Data Privacy API can support a broad range of customer IDs across multiple Adobe solutions. 

If a Data Subject submits a request along with an identifier (custom variable - prop or eVar), then Adobe Analytics scans then entire retained history of the data collected for the given identifier. For more details about how to configure custom IDs stored in Analytics props or eVars, please refer to the [Analytics documentation on namespaces](/help/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **How can Adobe Analytics Data Governance assist with processing Data Privacy requests?**

Data Governance is a new tool within Adobe Analytics that provides Data Controllers the ability to apply data controls and classifications across their Analytics data. This new tool empowers Adobe customers to customize the processing of their Data Privacy data access and data delete requests. In the Data Governance console, admins can define the desired settings that should be applied to various data columns that reside in Adobe Analytics. Once those labels are defined, Adobe will honor and process any downstream access or delete requests according to the customers' desired label settings. It is the responsibility of the Data Controller to review and council with their legal representatives regarding these label settings.

The Data Governance tool contains the following data labels:

* **Identity Data Labels**: Used to classify data that can identify an individual either directly or in combination with other data. (None, I1, I2)

* **Sensitive Data Labels**: Used to classify data as data that may be defined as sensitive under applicable law. (None, S1, S2) Note that currently the use of Sensitive Data in Adobe Analytics is generally prohibited except for precise geo-location data properly obtained under applicable law, which may be considered Sensitive Data in some jurisdictions.

* **Data Privacy Data Labels**: Used to define the fields that may contain personal identifiers for use in Data Privacy requests or that should be removed as part of a Data Privacy delete request. These labels may overlap the Identity and Sensitive Data labels, in some cases.  

For more information on Data Governance labels, see [Data Privacy Labels for Analytics Variables](/help/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **How can I validate that the Privacy Service requests are working properly to delete data from Adobe Analytics?**

Typically, Analytics customers set up some test report suites to verify functionality before it is released to the general public. Pre-production websites or apps send data into these test/dev/QA report suites to evaluate how things will work when the code releases before real traffic is sent to the production report suites.

However, with a normal configuration, GPDR request processing cannot be tested first on these test report suites, before applying requests to production report suites. This is because a Data Privacy request is automatically applied to all report suites in the Experience Cloud organization, which is often all report suites for your company.

Still, there are a few ways that you can test your Data Privacy processing prior to applying it to all your report suites:

* One option is to set up a separate Experience Cloud organization that contains only test report suites. Then use this Experience Cloud organization for your Data Privacy testing and your normal Experience Cloud organization for actual Data Privacy processing.

* Another option is to assign different namespaces to the IDs in your test report suites, versus those in your production report suites. For example, you can prefix each namespace with "qa-" in your test report suites. When you submit Data Privacy requests with only namespaces with the qa prefix, these requests will only run against your test report suites. Later, when you submit requests without the qa prefix, they will apply to your production report suites. **This is the recommended approach, unless you use the visitorId, AAID, ECID or customVisitorId namespaces. These namespaces are hardcoded and you cannot specify alternate names for them in your test report suites.**

+++

+++ **Where do I get started on getting Data Privacy ready with Adobe Analytics?**

For a step-by-step walkthrough to get ready for Data Privacy rules, see [Adobe Analytics Data Privacy Workflow](/help/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **How should Data Controllers think about consent when it comes to user engagement?**

GDPR and CCPA are good opportunities to re-consider your consent management strategy and practices. This includes determining when consent is needed and thinking about the value proposition for the user. Consider the value proposition for consumer privacy, which can help drive conversion and loyalty. The consent management space (e.g., tools, standards, best practices) is rapidly evolving, and is an area to watch. To minimize impact on user engagement, Controllers should work with vendors in this space as well as with their legal counsel, to ensure that they are following emerging laws and guidance on consent and cookies. Thinking about "experiential privacy" by using an on-brand, contextually relevant experience that sets out the value proposition of your data collection activities is a good strategy. 

You, as the Data Controller, are responsible for obtaining explicit consent from your Data Subjects before you collect data about them (possibly including Adobe Analytics data) and for implementing an [opt-out mechanism](https://www.adobe.com/privacy/opt-out.html#customeruse) on your web site. This lets your Data Subjects opt out of future Adobe Experience Cloud data collection.

+++

+++ **How should Data Controllers think about data retention when it comes to Data Privacy?**

Personal data generally should not be retained for longer than necessary to achieve the purpose for which it was collected. Adobe's General Terms apply a default 25-month data retention plan, unless a different data retention term is contractually agreed upon. Customers are required to set their data retention policy before Adobe can process a Data Privacy request.  

Each report suite's current data retention policy is displayed in the new Data Governance Admin UI. Customers should contact their Adobe representative if they need to adjust their data retention policy. Please refer to [Adobe Analytics Data Retention FAQs](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=en).

+++

+++ **Can a customer reduce or extend the default data retention period?**

Customers can request that their data be deleted sooner than 25 months by calling Customer Care. Customers can also extend data retention beyond 25 months by purchasing an extension. Extensions are available in increments of 1 additional year, up to a maximum of 8 additional years (10 years total). These extensions will require updated contract terms and additional fees.

+++

+++ **What privacy considerations should a Data Controller account for when personal data is exported from Adobe Analytics?**

If a customer uses Adobe Analytics Data Feeds to export data from Analytics into their enterprise data warehouse or into other systems outside of Adobe, it is the responsibility of the Customer (the Data Controller) to ensure that delete requests are applied to the data. This also applies to on-premise implementations of Adobe Data Workbench, where an ongoing Adobe Analytics data feed is populating the Data Workbench data. Adobe may provide tools to assist in finding and deleting the records from certain types of data feeds, including those used for Data Workbench, but it is still the Customer's (Data Controller) responsibility to ensure that the data is deleted consistent with their own, internal data retention and deletion policies.  

Please also consider cases where employees have downloaded Adobe Analytics reports that contain personal data. These reports may need to be updated or deleted if a Data Privacy-related delete request is received involving an ID that is present in the report. Customers should work with their own company's legal counsel to determine retention periods, and privacy and security requirements that should be applied to these types of documents.

+++

+++ **Some data we were not supposed to collect was accidentally sent into Adobe Analytics. Can we use the Data Privacy API to clean up this data?**

The [Data Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) has been provided to help you fulfill Data Privacy requests, which are time sensitive. Using this API for other purposes is not supported by Adobe and may impact Adobe's ability to provide timely turn-around of high priority, user-initiated Data Privacy requests for other Adobe customers. 

We ask that you do not use the Data Privacy API for other purposes such as clearing out data that was accidentally submitted across large groups of visitors. You should also be aware that any visitor who has a hit deleted (updated or anonymized) as a result of a Data Privacy deletion request will have their state information reset. The next time the visitor returns to your website, they will be a new visitor. All eVar attribution will start again, as will information such as visit numbers, referrers, first page visited, etc. This side effect is undesirable for situations where you want to clear out data fields, and highlights one reason why the Data Privacy API is inappropriate for this use.  

Please contact your Account Manager (CSM) to coordinate with our Engineering Architect consulting team to further review & provide level of effort to remove any PII or data issues.

+++

+++ **Our legal team has determined that values we have been collecting in a variable for years no longer comply with our updated privacy policy. Can we use the Data Privacy API to clear out all values from this variable?**

The [Data Privacy Service API](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) has been provided to help you fulfill Data Privacy requests, which are time sensitive. Using this API for other purposes is not supported by Adobe and may impact Adobe's ability to provide timely turn-around of high priority, user-initiated Data Privacy requests for other Adobe customers. We ask that you do not use the Data Privacy API for other purposes such as clearing out data that was accidentally submitted across large groups of visitors.

You should also be aware that any visitor who has a hit deleted (updated or anonymized) as a result of a Data Privacy deletion request will have their state information reset. The next time the visitor returns to your website, they will be a new visitor. All eVar attribution will start again, as will information such as visit numbers, referrers, first page visited, etc. This side effect is undesirable for situations where you want to clear out data fields, and highlights one reason why the Data Privacy API is inappropriate for this use.  

Please contact your Account Manager (CSM) to coordinate with our Engineering Architect consulting team to further review and provide level of effort to remove any PII or data issues.

+++

Additional Data Privacy Resources:

* [GDPR Common Terms](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf) 
* Experience Cloud Data Privacy [Care Package](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) 
* Experiential Privacy [Blog Post](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
