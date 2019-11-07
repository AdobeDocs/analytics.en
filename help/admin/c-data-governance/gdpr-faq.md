---
description: null
title: Frequently asked questions
uuid: 1cd41253-d74f-4b92-92e6-56f9afa3df85
---

# Frequently asked questions

<table id="table_FA37A4B3960C4181B9CCDB569A476936"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>How does Adobe Analytics support access and delete requests for end users (Data Subjects) validated by customers (Data Controllers)?</b> </p> </td> 
   <td colname="col2"> <p>When various Data Privacy rules (GDPR, CCPA) take eﬀect, Adobe Analytics will support processing verified requests submitted by Data Controllers to the Experience Cloud Data Privacy API to enable a more automated process. Adobe's Data Privacy API is designed to help process individual rights requests (e.g., access and delete requests) for our customers' data stored across Adobe Experience Cloud solutions. It is flexible and scales according to the number of data access and delete requests your company receives from data subjects. Also, the Data Privacy API allows the customer to check the status on how the data access and delete requests are being fulfilled. </p> <p>For more details see <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html"> Data Privacy API documentation. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Who is responsible for receiving, accepting, and fulfilling Data Privacy requests from end users?</b> </p> </td> 
   <td colname="col2"> <p>The Data Controller (i.e. The Adobe Customer) has the sole responsibility for providing data subjects with personal data in response to an individual rights request under Data Privacy. The Data Controller also has the sole responsibility for receiving requests and accepting the request - validating the data subject's identity and then fulfilling the request, part of which may involve contacting Adobe with data subjects' IDs that may be associated with data stored in Adobe Analytics. As the Data Processor, Adobe must provide reasonable assistance to the controller to process verified requests within an acceptable amount of time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>How will Adobe Customers (Data Controllers) find out which Data Privacy requests map to which IDs in Adobe Analytics for Data Privacy processing?</b> </p> </td> 
   <td colname="col2"> <p>The data controllers will determine how to resolve identity for requests from the data subjects. Consider deploying <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> Adobe's Data Privacy ID Retrieval Tag. </a> Your development teams will save time by using our Data Privacy ID retrieval tag to capture user IDs (cookie IDs), and then using our Data Privacy API to send those user IDs to the relevant solutions in the Adobe Experience Cloud for Data Privacy request processing. </p> <p>The Data Privacy API can support a broad range of customer IDs across multiple Adobe solutions. If a data subject submits a request along with an identifier (custom variable - prop or eVar), then Adobe Analytics will scan then entire retained history of the data collected for the given identifier. For more details about how to configure custom IDs stored in Analytics props or eVars, please refer to the Analytics documentation on <a href="/help/admin/c-data-governance/gdpr-namespaces.md"> Namespaces.</a>
    </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>How can Adobe Analytics Data Governance assist with processing Data Privacy requests?</b> </p> </td> 
   <td colname="col2"> <p>Data Governance is a new tool within Adobe Analytics that provides data controllers the ability to apply data controls and classifications across their Analytics data. This new tool empowers Adobe customers to customize the processing of their Data Privacy data access and data delete requests. In the Data Governance console, admins can define the desired settings that should be applied to various data columns that reside in Adobe Analytics. Once those labels are defined, Adobe will honor and process any downstream access or delete requests according to the customers' desired label settings. It is the responsibility of the data controller to review and council with their legal representatives regarding these label settings. Adobe Analytics encourages clients to set up data labeling correctly in advance of GDPR eﬀective date, which is May 25th, 2018 to allow customize completion of request utilizing Data Privacy API. </p> <p>The Data Governance tool contains the following data labels: </p> 
    <ul id="ul_F25B00EB020B4A639628FB884D0CB4F9"> 
     <li id="li_C295A396685340369D730D696FE6FC13"> <a href="/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels"> Identity Data Labels: </a> Used to classify data that can identify an individual either directly or in combination with other data. (None, I1, I2) </li> 
     <li id="li_6D9A25139D3342CA82AAA64BC01AD368"> <a href="/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels"> Sensitive Data Labels: </a> Used to classify data as data that may be defined as sensitive under applicable law. (None, S1, S2) Note that currently the use of Sensitive Data in Adobe Analytics is generally prohibited except for precise geo-location data properly obtained under applicable law, which may be considered Sensitive Data in some jurisdictions. </li> 
     <li id="li_C69935AAC36741D8A902D14F75E896D6"> <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> Data Privacy Data Labels: </a> Used to define the fields that may contain personal identifiers for use in Data Privacy requests or that should be removed as part of a Data Privacy delete request. These labels may overlap the Identity and Sensitive Data labels, in some cases. </li> 
    </ul> <p>For more information on Data Governance labels, see <a href="/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels"> Data Privacy Labels for Analytics Variables. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Where do I get started on getting Data Privacy ready with Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>For a step-by-step walkthrough to get ready for Data Privacy rules, see <a href="/help/admin/c-data-governance/an-gdpr-workflow.md"> Adobe Analytics Data Privacy Workflow. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>How should data controllers think about consent when it comes to user engagement?</b> </p> </td> 
   <td colname="col2"> <p>GDPR and CCPA are good opportunities to re-consider your consent management strategy and practices, including determining when consent is needed and thinking about the value proposition for the user. Consider the value proposition for consumer privacy, which can help drive conversion and loyalty. </p> <p>The consent management space (e.g., tools, standards, best practices) is rapidly evolving, and is an area to watch. To minimize impact on user engagement, controllers should work with vendors in this space and with their counsel, and follow emerging EU laws and guidance on consent and cookies. Thinking about "experiential privacy" by using an on-brand, contextually relevant experience that sets out the value proposition of your data collection activities is a good strategy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>How should data controllers think about data retention when it comes to Data Privacy?</b> </p> </td> 
   <td colname="col2"> <p>Data Privacy generally provides that personal data generally should not be retained for longer than necessary to achieve the purpose for which it was collected. </p> <p>As Adobe detailed in its customer communication in February, we will apply a 25-month data retention plan to most customers unless other arrangements have been made (subject to customer notification and authorization). Customers will be required to set their data retention policy before Adobe can process Data Privacy request. </p> <p>Adobe Analytics requires customers to set their data retention to process their Data Privacy requests. Each report suite's current data retention policy is displayed in the new Data Governance Admin UI. Customers should contact their Adobe representative if they need to adjust their data retention policies. Please, refer to <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Adobe Analytics Data Retention FAQS. </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Can a customer reduce or extend the Default Data Retention Period?</b> </p> </td> 
   <td colname="col2"> <p>Customers can request that their data be deleted sooner than 25 months by calling customer care. Customers can extend data retention beyond 25 months by purchasing an extension.</p><p>
   Extensions are available in increments of 1 (one) additional year, up to a maximum of 8 (eight) additional years (10 years total). These extensions may require updated contract terms and additional fees.
 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> What privacy considerations should a Data Controller account for when personal data is exported from Adobe Analytics?</b> </p> </td> 
   <td colname="col2"> <p>If a customer uses Adobe Analytics Data Feeds to export data from Analytics into their enterprise data warehouse or into other systems outside of Adobe, it is the responsibility of the Customer (the Data Controller) to ensure that delete requests are applied to the data. This also applies to on-premise implementations of Adobe Data Workbench (Insight), where an ongoing Adobe Analytics data feed is populating the Data Workbench data. Adobe may provide tools to assist in finding and deleting the records from certain types of data feeds, including those used for Data Workbench, but it is still the Customer's (Data Controller) responsibility to ensure that the data is deleted consistent with their own, internal data retention and deletion policies. </p> <p>Please also consider cases where employees may have downloaded Adobe Analytics reports that contain personal data. These reports may need to be updated or deleted if a Data Privacy-related delete request is received involving an ID that may be present in the report. Customers should work with your company's legal counsel to determine retention periods, and privacy and security requirements that should be applied to these types of documents. </p> </td> 
  </tr> <tr> 
   <td colname="col1"> <p><b> Some data we were not supposed to collect was accidentally sent into Adobe Analytics. Can we use the Data Privacy API to cleanup this data?</b> </p> </td><td colname="col2"> <p>The Data Privacy API has been provided to help you fulfill Data Privacy requests, which are time sensitive. Using this API for other purposes is not supported by Adobe and may impact Adobe's ability to provide timely turn-around of high priority, user-initiated Data Privacy requests for other Adobe customers. We ask that you do not use the Data Privacy API for other purposes such as clearing out data that was accidentally submitted across large groups of visitors.</p> <p>You should also be aware that any visitor who has a hit deleted (updated or anonymized) as a result of a Data Privacy deletion request will have their state information reset. The next time the visitor returns to your website, they will be a new visitor. All eVar attribution will start again, as will information such as visit numbers, referrers, first page visited, etc. This side effect is undesirable for situations where you want to clear out data fields, and highlights one reason why the Data Privacy API is inappropriate for this use. </p> <p>Please contact your Account Manager (CSM) to coordinate with our Engineering Architect consulting team to further review & provide level of effort to remove any PII or data issues.</p></td></tr> <tr> 
   <td colname="col1"> <p><b> Our legal team has determined that values we have been collecting in a variable for years, no longer comply with our updated privacy policy. Can we use the Data Privacy API to clear out all values from this variable?</b> </p> </td><td colname="col2"> <p>The Data Privacy API has been provided to help you fulfill Data Privacy requests, which are time sensitive. Using this API for other purposes is not supported by Adobe and may impact Adobe's ability to provide timely turn-around of high priority, user-initiated Data Privacy requests for other Adobe customers. We ask that you do not use the Data Privacy API for other purposes such as clearing out data that was accidentally submitted across large groups of visitors.</p> <p>You should also be aware that any visitor who has a hit deleted (updated or anonymized) as a result of a Data Privacy deletion request will have their state information reset. The next time the visitor returns to your website, they will be a new visitor. All eVar attribution will start again, as will information such as visit numbers, referrers, first page visited, etc. This side effect is undesirable for situations where you want to clear out data fields, and highlights one reason why the Data Privacy API is inappropriate for this use. </p> <p>Please contact your Account Manager (CSM) to coordinate with our Engineering Architect consulting team to further review & provide level of effort to remove any PII or data issues.</p></td>
 </tbody> 
</table>

Additional Data Privacy Resources:

* [GDPR Common Terms](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf) 
* Experience Cloud Data Privacy [Care Package](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) 
* Experiential Privacy [Blog Post](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
