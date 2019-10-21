---
description: null
seo-description: null
seo-title: Attribution IQ FAQ
title: Attribution IQ FAQ
uuid: 90961172-869d-4ed3-aba5-52374e53b603
---

# Attribution IQ FAQ

<table id="table_590341C2F0DA4511ADEFDC1DB49CD248"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Why is the “None” line item sometimes getting more credit than I expected when I use the new attribution models?</b> </p> </td> 
   <td colname="col2"> <p>A: This is likely due to the reporting window you’ve selected as described <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md#section_BC71DA030E45487AA3C3F6ED247A3C4A"  > here </a>. This most often occurs when your reporting window starts on the first day of the month and you’re using a Visitor (Reporting Window) lookback. To capture additional attribution lookback (and reduce the “None” line item), try including a longer time range in your reporting window. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: I sometimes see dates outside of my reporting window show up in my report when using attribution models. Why?</b> </p> </td> 
   <td colname="col2"> <p>A: These extra dates are an artifact of the visitor reporting lookback window described <a href="../../../analyze/analysis-workspace/attribution-iq/attribution.md"  > here </a>. The article <a href="https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html"  > Data appearing outside reporting window </a> explains why this currently happens. Adobe Analytics will filter out these extra rows in an upcoming release. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Can I use a custom lookback window with my attribution models?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, attribution models rely on either a visitor or visit lookback window - but either of these lookback windows are adjustable by either changing the reporting date range (for visitor lookback) or by using a custom visit definition as part of Virtual Report Suites and <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html"  > Context-Aware Sessions </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: When should I use a “visit” attribution lookback vs. a “visitor” attribution lookback?</b> </p> </td> 
   <td colname="col2"> <p>A: The choice of attribution lookback really depends on your use case. If your conversion typically has a longer consideration cycle (something that takes longer than a single visit), we recommend using a visitor lookback, or creating a VRS with a longer visit that more accurately reflects that consideration cycle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Are attribution models available in Data Feeds or Data Warehouse?</b> </p> </td> 
   <td colname="col2"> <p>A: No. Because attribution models are calculated at report time using <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html"  > Report Time Processing </a>, it’s not possible to have them reflected in Data Feeds or Data Warehouse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Are attribution models only available if I’m using a Virtual Report Suite with Report Time Processing enabled?</b> </p> </td> 
   <td colname="col2"> <p>A: No, while attribution models leverage <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html"  > Report Time Processing </a> on the backend, we’ve made them available to both VRS and base report suites for convenience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Does Attribution IQ in Analysis Workspace support a data-driven or algorithmic attribution model?</b> </p> </td> 
   <td colname="col2"> <p>A: This is not yet available in Analysis Workspace, but it’s something we are actively looking into. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Are any dimensions or metrics not supported by Attribution IQ?</b> </p> </td> 
   <td colname="col2"> <p>A: Attribution IQ is supported on all dimensions.</p> 
    <p>Metrics that are <u>not</u> supported (primarily because they wouldn’t make sense) include: </p> 
    <ul id="ul_B12A1291DEEF41FDBAD110C4A9265234"> 
     <li id="li_245571C5377C45ADBAE6F735B91FCD1F"> Unique Visitors </li> 
     <li id="li_000CA7680A0745D9860CA7D5F62288D4">Visits </li> 
     <li id="li_53CAD3ECAE54451BBB0750FB62AF1243">Occurrences </li> 
     <li id="li_C589008CA92E4C69866E85EEEC88EF90"> Page Views </li> 
     <li id="li_ACF8D24E3AC746E280DB0F71D4B772A3">A4T metrics </li> 
     <li id="li_78BFE0A4F8024301A218C0415537F632">Time Spent metrics </li> 
     <li id="li_29774EEFE9A04759B7929EA35AA9BEAD">Bounces </li> 
     <li id="li_B163C6F24240465F85AB5C9792F0F013">Bounce rate </li> 
     <li id="li_CF065E227A634C77BC2C48C2A6EC849A">Entries </li> 
     <li id="li_ED962C5063B047F185EFC58EB43C661F">Exits </li> 
     <li id="li_029F6D09433F48A38303E5C96E77480B">Pages Not Found </li> 
     <li id="li_8410AF29208247B5B3E49F72208913BA">Searches </li> 
     <li id="li_8421F1D5F58148D98B1AB5C04FCCA9CF">Single Page Visits </li> 
     <li id="li_50D4EA0FF2E6438C8DD2A1B2EAD7B9D7">Single Access </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: How does Attribution IQ differ from attribution in Data Workbench?</b> </p> </td> 
   <td colname="col2"> <p>A: Data Workbench incrementally offers: </p> 
    <ul id="ul_5A8C979CDCD04FF5B9625C84B2678CC7"> 
     <li id="li_115DC58D4BDF40A4A0036E76F6E64158">The ability to attribute across more visitor-level data sources, such as ad impressions and point of sale. </li> 
     <li id="li_C31891A4D5594D93AF97340F6D3A2E3E">Algorithmic ( <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html"  > best fit </a>) modeling. Attribution IQ includes rules-based models only. </li> 
     <li id="li_749D5D11B34E40E9AB53908A38979CAA">Additional visualizations, such as <a href="https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html"  > latency tables </a>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Does Attribution IQ work with data sources?</b> </p> </td> 
   <td colname="col2"> <p>A: Currently, Attribution IQ works with data sources other than summary-level data sources. </p> <p> Because summary-level data sources do not tie to an Analytics visitor identifier, advanced attribution is not possible. Transaction ID data sources are also supported, unless they are used in a Virtual Report Suite with <a href="https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html"  > report-time processing </a> enabled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Does Attribution IQ work with the <a href="https://marketing.adobe.com/resources/help/en_US/analytics/advertising/overview.html"  > Advertising Analytics </a> integration?</b> </p> </td> 
   <td colname="col2"> <p>A: The integrated metrics - which include impressions, cost, clicks, average position, and average quality score - are summary-level data sources, and therefore incompatible with Attribution IQ. However, the metadata dimensions (e.g. match type and keyword) will work with attribution when used with standard Analytics events or metrics. </p> </td> 
  </tr> 
 </tbody> 
</table>

