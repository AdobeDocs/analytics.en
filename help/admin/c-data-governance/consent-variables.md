# Consent Management Variables

To provide additional assistance in managing privacy data, a set of reserved variables are available to be used in conjunction with specific context data variables. 
These consent management variables provide an easy to use framework for capturing the consent status on each analytics hit.

## Variables

* Consent Management Opt-Out
   * Reserved Variable: List Prop
   * Type: Comma delimited string
   * Contains:
      * contextData.['cm.ssf']=1 displayed as SSF
      * contextData.['opt.dmp']=N displayed as DMP
      * contextData.['opt.sell']=N displayed as SELL

* Consent Management Opt-In
   * Reserved Variable: List Prop
   * Type: Comma delimited string
   * Contains:
      * contextData.['opt.dmp']=Y displayed as DMP
      * contextData.['opt.sell']=Y displayed as SELL

## Reporting

The Consent Management Variables can be enabled through a new Privacy setting available within the Analytics Admin Console.

Each report suite can be configured to:
1. In Reports & Analytics click Admin > Report Suites.
2. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings > Privacy] 

    `![](replace with correct screen grab)`

3. Need to see final UI for next steps

## Implementation

Three context data variables have been pre-defined to work with the consent management reserved variables.  It is up to each implementation engineer to determine how to manage and persist the setting of these variables.  

See [Context Data Variables](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) for general guidance on implementing context data variables.

### SSF

   * Context Data: contextData.['cm.ssf']
   * Accepted Values:  
      * `1` - When sending the value `1`, this indicates that Server Side Forwarding is in an opt-out state. The value `1` paired with this variable will block the sharing of this hit with Adobe Audience Manager. See [AAM ePrivacy Compliance.](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
      * No other values are accepted for this parameter

### DMP
   * Context Data: contextData.['opt.dmp']
   * Accepted Values:  
      * `N` - When sending the value `N`, this indicates that the consumer is opting out of sharing to data management platforms. Note this does not current block sharing to AAM.  Use SSF for that functionality.
      * `Y` - When sending the value `Y`, this indicates that the consumer is opting in to sharing to data management platforms.

### SELL

   * Context Data: contextData.['opt.sell']
   * Accepted Values:  
      * `N` - When sending the value `N`, this indicates that the consumer is opting out of the sharing or selling of the data to third parties.
      * `Y` - When sending the value `Y`, this indicates that the consumer is opting in to the sharing or selling of the data to third parties.

