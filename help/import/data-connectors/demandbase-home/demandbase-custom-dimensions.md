---
description: Lists optional dimension identifiers that can be given in Step 4 of the Adobe Integration wizard.
seo-description: Lists optional dimension identifiers that can be given in Step 4 of the Adobe Integration wizard.
seo-title: Demandbase Custom Dimensions
title: Demandbase Custom Dimensions
uuid: d1621046-3aa2-46b9-a536-4a8fb792b69f
---

# Demandbase Custom Dimensions{#demandbase-custom-dimensions}

Lists optional dimension identifiers that can be given in Step 4 of the Adobe Integration wizard.

If you are unsure of the exact API ID to enter into the wizard, please consult with your Demandbase representative.

>[!IMPORTANT]
>
>It is strongly recommended that you do NOT include IP Address as a custom dimension. The extremely high number of unique values may cause performance issues with reporting. In addition, IP Address is already offered as a reporting option through Adobe data warehouse reporting.

<table id="table_3B44A18BE5FE45BC83389F89B48D9B97"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dimension </th> 
   <th colname="col2" class="entry"> API IDs </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISP </td> 
   <td colname="col2"> isp </td> 
   <td colname="col3"> Indicates whether the organization identified is classified as an ISP. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Marketing Alias </td> 
   <td colname="col2"> marketing_alias </td> 
   <td colname="col3"> Cleaned and/or shortened organization name (32 characters or less) for use in ads, messages or marketing copy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Account Watch Tags </td> 
   <td colname="col2"> watch_list (custom) </td> 
   <td colname="col3">Unlimited set of tags defined by client that may be added to their API response data, by organization. <p><b>Example</b>: if you have a Watch Tag called Q4 Target, the API field would be </p> <code> watch_list_q4_target</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fortune 1000 </td> 
   <td colname="col2"> fortune_1000 </td> 
   <td colname="col3"> Indicates whether the organization is on the Fortune 1000 list. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Forbes 2000 </td> 
   <td colname="col2"> forbes_2000 </td> 
   <td colname="col3"> Indicates whether the organization is on the Forbes 2000 list. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Employee Count </td> 
   <td colname="col2"> employee_count </td> 
   <td colname="col3"> The number of people employed at the organization. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Annual Sales </td> 
   <td colname="col2"> annual_sales </td> 
   <td colname="col3"> For public entities, annual revenue is based on company-reported public records for the global HQ on all locations. For privately-held organizations, it is based on consensus estimate for the yearly sales revenue number. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Phone number </td> 
   <td colname="col2"> phone </td> 
   <td colname="col3"> The telephone number of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Street address </td> 
   <td colname="col2"> street_address </td> 
   <td colname="col3"> The street address of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> City </td> 
   <td colname="col2"> city </td> 
   <td colname="col3"> The city of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> State </td> 
   <td colname="col2"> state </td> 
   <td colname="col3"> The state of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Country Code </td> 
   <td colname="col2"> country_code </td> 
   <td colname="col3"> The ISO two-character country code of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Country Name </td> 
   <td colname="col2"> country_name </td> 
   <td colname="col3"> The string value country name of the country for the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Zip </td> 
   <td colname="col2"> zip </td> 
   <td colname="col3"> The zip code of the country/state for the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Website </td> 
   <td colname="col2"> web_site </td> 
   <td colname="col3"> The URL used by the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stock Ticker </td> 
   <td colname="col2"> stock_ticker </td> 
   <td colname="col3"> The stock ticker if the organization identified is publicly traded. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Primary SIC Code </td> 
   <td colname="col2"> primary_sic </td> 
   <td colname="col3"> Consensus SIC code assigned for the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude </td> 
   <td colname="col2"> latitude </td> 
   <td colname="col3"> Latitude for the location of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Longitude </td> 
   <td colname="col2"> longitude </td> 
   <td colname="col3"> Longitude for the location of the organization identified. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Traffic </td> 
   <td colname="col2"> traffic </td> 
   <td colname="col3"> The amount of website traffic, estimated to low, medium or high or very high. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2B </td> 
   <td colname="col2"> b2b </td> 
   <td colname="col3"> Indicates that the identified company primarily sells to other businesses. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> B2C </td> 
   <td colname="col2"> b2c </td> 
   <td colname="col3"> Indicates that the identified company primarily sells to consumers or individuals. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Technology Insight </td> 
   <td colname="col2"> ??? </td> 
   <td colname="col3"> Up to 75 technology categories that are defined by customers via category, vendor and products for the use of targeting and/or customizing ads, messages or marketing copy. </td> 
  </tr> 
 </tbody> 
</table>

