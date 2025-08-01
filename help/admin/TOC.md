---
product: analytics
audience: admin
user-guide-title: Analytics Admin Guide
breadcrumb-title: Admin Guide
user-guide-description: Learn about Analytics administration tasks, such managing users and products in the Experience Cloud Admin Console, configuring report suites, and more.
---

# Adobe Analytics Admin Guide {#admin}

+ [Analytics Admin Guide](home.md)
+ [Analytics Release Notes](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html)
+ Adobe admin console {#admin-console}
  + [Overview](admin-console/home.md)
  + [Adobe Analytics first admin guide](admin-console/first-admin-guide.md)
  + [Administrator roles in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
  + Analytics tools permissions summary {#permissions}
    + [Product profiles for Adobe Analytics](admin-console/permissions/product-profile.md)
    + [Product profile permissions for Report Suite Tools](admin-console/permissions/report-suite-tools.md)
    + [Product profile permissions for Analytics Tools](admin-console/permissions/analytics-tools.md)
+ Analytics admin tools {#admin-tools}
  + [Admin tools overview](admin/c-admin-tools.md)
  + [Code Manager](admin/code-manager-admin.md)
  + [Analytics Inventory](admin/analytics-inventory.md)
  + [Data Sources](admin/data-sources.md)
  + [Exclude by IP address](admin/exclude-ip.md)
  + [Logs](admin/logs.md)
  + Reporting Activity Manager {#reporting-activity-manager}
    + [Overview](admin/reporting-activity-manager/reporting-activity-overview.md)
    + [View reporting activity](admin//reporting-activity-manager/reporting-activity.md)
    + [Cancel reporting requests](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
  + Component migration {#component-migration}
    + [Prepare for migration](admin/component-migration/prepare-component-migration.md)
    + [Migration workflow](admin/component-migration/component-migration.md)
  + Report Suite manager {#manage-report-suites}
    + Edit settings of a report suite {#edit-report-suite}
      + General {#report-suite-general}
        + [General Account settings](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
        + [Internal URL Filters](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
        + [Customize Calendar](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
        + Paid Search Detection {#paid-search-detection}
          + [Paid search detection overview](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
          + [Configure paid search detection](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
        + Processing Rules {#processing-rules}
          + [Overview](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)
          + [Interface](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-interface.md)
          + [View history](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-view-history.md)
          + [Copy rules](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-copy.md)
          + [Available dimensions and metrics](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-variables.md)
          + [Use cases](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-use-cases.md)
        + Bot Rules {#bot-removal}
          + [Bot removal](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
          + [Understand and configure bot rules](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
          + [Common bot signatures](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
          + [Bot exclusion methods](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
        + [Privacy Settings](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
        + [Timestamps Configuration](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
        + Server-Side Forwarding {#server-side-forwarding}
          + [Server-side forwarding overview](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
          + [GDPR/ePrivacy compliance and server-side forwarding](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
          + [Requirements for server-side forwarding](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
          + [Server-side forwarding data and code reference](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
          + [How to verify your server-side forwarding implementation](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
          + [Server-side forwarding FAQ](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
      + Traffic {#traffic-variables}
        + [Traffic Variables](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
        + [Traffic Classifications](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
        + [Custom report descriptions](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
      + Conversion {#conversion-variables}
        + [Conversion Variables](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
        + [Finding Methods](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
        + [Conversion Classifications](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
        + Unique Visitor Variable {#unique-visitor-variable}
          + [Specify the Unique Visitor variable](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
          + [Use case - extracting Visitor IDs](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
        + [Success events](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
        + [Classification Hierarchies](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
        + [List Variables](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
        + [Merchandising eVars](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
      + Marketing Channels {#marketing-channels}
        + [Marketing Channel Manager](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
        + [Marketing Channel Processing Rules](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
        + [Marketing Channel Classifications](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
        + [Marketing Channel Expiration](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
      + Traffic Management {#traffic-management}
        + [Overview](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
        + [Schedule Spike](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
        + [Permanent Traffic](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)  
      + [Default Metrics](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
      + App Management {#app-management}
        + [App Reporting](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
        + [App Classifications](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
      + [Media Management](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
      + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
      + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
      + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
      + [Privacy Reporting](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
      + Document Cloud Management {#doc-cloud-mgt}
        + [Configure Document Cloud with Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
        + [Configure Document Cloud reporting](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
      + [Advertising Analytics Configuration](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
      + Real-Time {#real-time-reports}
        + [Real-time reports overview](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
        + [Real-time reports configuration](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
        + [Supported real-time metrics and dimensions](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
    + [Manage report suites](admin/c-manage-report-suites/report-suites-admin.md)
    + [Global report suites](admin/c-manage-report-suites/rollup-report-suite.md)
    + [Save a report suite search](admin/c-manage-report-suites/t-report-suite-saved-search.md)
    + [Download report suite settings](admin/c-manage-report-suites/t-download-rs-settings.md)
    + New report suite {#c-new-report-suite}
      + [Create a report suite](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
      + [Create a report suite group](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
      + [New report suite - settings](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
      + [Settings not copied from a source report suite](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
    + Report suite templates {#report-suite-templates}
      + [Report suite templates overview](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
      + [Aggregator portal](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
      + [Commerce](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
      + [Content and Media](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
      + [Default template](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
      + [Financial Services](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
      + [Job portal](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
      + [Lead Generation](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
      + [Support Media](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
  + Company Settings {#company-settings}
    + [Company Settings overview](admin/company/c-company-settings.md)
    + [Security Manager](admin/company/security-manager.md)
    + [Web Services](admin/company/web-services-admin.md)
    + [Report Builder reports](admin/company/report-builder-reports-admin.md)
    + [Single sign-on](admin/company/single-signon-admin.md)
    + [Hide report suites](admin/company/c-hide-report-suites.md)
    + [Preferences manager](admin/company/preferences-manager.md)
    + [Pending actions](admin/company/pending-actions-admin.md)
    + [Feature access levels](admin/company/feature-access-levels.md)
  + Data Governance Privacy Labeling {#data-governance}
    + [Adobe Analytics Data Privacy workflow](admin/c-data-governance/an-gdpr-workflow.md)
    + [Frequently asked questions](admin/c-data-governance/gdpr-faq.md)
    + Data labeling {#data-labels}
       + [Data Privacy labels for Analytics components](admin/c-data-governance/data-labeling/gdpr-labels.md)
       + [Label report suite data](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
       + [View/manage report suite's privacy labels](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
       + [Labeling best practices](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
       + [Labeling example](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
       + [Namespaces](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
    + [CNIL Consent Exemption](admin/c-data-governance/cnil-consent-exemption.md)
  + Server Call Usage {#server-call-usage}
    + [Server call usage overview](admin/c-server-call-usage/overage-overview.md)
    + [View current server call usage](admin/c-server-call-usage/server-call-usage-dashboard.md)
    + [View report suite usage](admin/c-server-call-usage/report-suite-usage.md)
    + [Server call usage alerts](admin/c-server-call-usage/scu-alerts.md)
    + [Server call usage FAQ](admin/c-server-call-usage/overage-faq.md)
  + User and Product Management (Legacy) {#user-product-management}
    + [User and Product Management (Legacy)](admin/user-management2/user-management.md)
    + [Manage legacy user accounts, assets and expirations](admin/user-management2/users-assets.md)
    + Migrate users to Adobe Admin Console {#migrate-users}
      + [Analytics User Migration to the Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
      + [Migrate Analytics user accounts for Adobe IDs](admin/user-management2/user-migration/t-migrate-users.md)
      + [Migrate Analytics user accounts for Enterprise and Federated IDs](admin/user-management2/user-migration/migrate-enterprise.md)
      + [Disable legacy logins](admin/user-management2/user-migration/t-disable-legacy-login.md)
      + [APIs Affected by the Migration](admin/user-management2/user-migration/developer.md)  
+ [Admin API](c-admin-api/c-admin-api.md)
+ [Adobe Analytics 1.4 API EOL FAQ](c-admin-api/c-admin-14-api-eol.md)

