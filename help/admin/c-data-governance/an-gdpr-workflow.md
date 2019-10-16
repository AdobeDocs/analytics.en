---
description: null
seo-description: null
seo-title: Adobe Analytics Data Privacy workflow
title: Adobe Analytics Data Privacy workflow
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
---

# Adobe Analytics Data Privacy workflow

Welcome to Adobe Analytics and Data Privacy readiness! This workflow outlines the steps you need to take to make your Adobe Analytics implementation ready to support your data subjects' Data Privacy access and delete rights. 

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">List Item </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Assign identity, sensitivity, and data governance labels to each variable in a report suite. </p> <p>Note:  Remember that Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. You may also need to review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites may change the way that existing variables are used, which may also necessitate updates to labels. </p> </td> 
   <td colname="col3"> <p> Follow the instructions in <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Connect to the Adobe Data Privacy API and submit Access and Delete Requests. </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> View and manage your report suite's Data Privacy settings. </p> </td> 
   <td colname="col3"> <p>Follow the instructions in <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Task Description | Links to Instructions and More Information |
|--- |--- |
|**Step 1**: Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization.  Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company.|Refer to [Map report suites to an organization.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)|
|**Step 2**Set your data retention policy.|A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests.  For more information, see this [Analytics Data Retention FAQ.](/help/technotes/data-retention.md)|
|**Step 3**: Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion.|Read these topics in this documentation set:<ul><li>[Data Privacy Labels for Analytics Variables](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Labeling Best Practices](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul>|
|**Step 4**: Assign identity, sensitivity, and data governance labels to each variable in a report suite.  Note:  Remember that Labeling needs to be reviewed each time a new report suite is created or when new variable is enabled within an existing report suite. You may also need to review the labeling when new solution integrations are enabled, as they can expose new variables that may require labeling. A re-implementation of your mobile apps or websites may change the way that existing variables are used, which may also necessitate updates to labels.|Follow the instructions in [Label Report Suite Data.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md)|
|**Step 5**: Connect to the Adobe Data Privacy API and submit Access and Delete Requests.|As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html) You can submit any Analytics identifiers (as described in the section [Labeling Best Practices](/help/admin/c-data-governance/gdpr-analytics-ids.md)) in the requests along with their respective namespace IDs (data source IDs).|
|**Step 6**: View and manage your report suite's Data Privacy settings.|Follow the instructions in [View Report Suite's Data Governance Settings.](/help/admin/c-data-governance/gdpr-view-settings.md)|
