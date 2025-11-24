---
product: analytics
audience: admin
user-guide-title: Analytics Admin Guide
breadcrumb-title: Admin Guide
user-guide-description: Learn about Analytics administration tasks, such managing users and products in the Experience Cloud Admin Console, configuring report suites, and more.
---

# Adobe Analytics Admin Guide {#admin}

+ [Analytics admin guide](home.md)
+ [Analytics release notes](https://experienceleague.adobe.com/en/docs/analytics/release-notes/latest)
+ Adobe admin console {#admin-console}
  + [Overview](admin-console/home.md)
  + [Adobe Analytics first admin guide](admin-console/first-admin-guide.md)
  + [Administrator roles in Adobe Analytics](admin-console/admin-roles-in-analytics.md)
  + Analytics tools permissions summary {#permissions}
    + [Product profiles for Adobe Analytics](admin-console/permissions/product-profile.md)
    + [Product profile permissions for Report Suite Tools](admin-console/permissions/report-suite-tools.md)
    + [Product profile permissions for Analytics Tools](admin-console/permissions/analytics-tools.md)
+ Analytics admin tools {#admin-tools}
  + [Admin tools overview](tools/c-admin-tools.md)
  + [Code Manager](tools/code-manager-admin.md)
  + [Analytics Inventory](tools/analytics-inventory.md)
  + [Data Sources](tools/data-sources.md)
  + [Exclude by IP address](tools/exclude-ip.md)
  + [Logs](tools/logs.md)
  + Reporting Activity Manager {#reporting-activity-manager}
    + [Overview](tools/reporting-activity-manager/reporting-activity-overview.md)
    + [View reporting activity](tools//reporting-activity-manager/reporting-activity.md)
    + [Cancel reporting requests](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
  + Component migration {#component-migration}
    + [Prepare for migration](tools/component-migration/prepare-component-migration.md)
    + [Migration workflow](tools/component-migration/component-migration.md)
  + Report Suite manager {#manage-report-suites}
    + Edit settings of a report suite {#edit-report-suite}
      + General {#report-suite-general}
        + [General Account settings](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
        + [Internal URL Filters](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
        + [Customize Calendar](tools/manage-rs/edit-settings/general/custom-calendar.md)
        + Paid Search Detection {#paid-search-detection}
          + [Paid search detection overview](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
          + [Configure paid search detection](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
        + Processing Rules {#processing-rules}
          + [Overview](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
          + [Interface](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
          + [View history](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
          + [Copy rules](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
          + [Available dimensions and metrics](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
          + [Use cases](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
        + Bot Rules {#bot-removal}
          + [Bot removal](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
          + [Understand and configure bot rules](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
          + [Common bot signatures](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
          + [Bot exclusion methods](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
        + [Privacy settings](tools/manage-rs/edit-settings/general/privacy-settings.md)
        + [Timestamps configuration](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
        + Server-Side Forwarding {#server-side-forwarding}
          + [Server-side forwarding overview](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
          + [GDPR/ePrivacy compliance and server-side forwarding](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
          + [Requirements for server-side forwarding](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
          + [Server-side forwarding data and code reference](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
          + [How to verify your server-side forwarding implementation](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
          + [Server-side forwarding FAQ](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
      + Traffic {#traffic-variables}
        + [Traffic Variables](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
        + [Traffic Classifications](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
        + [Custom report descriptions](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
      + Conversion {#conversion-variables}
        + [Conversion Variables](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
        + [Finding Methods](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
        + [Conversion Classifications](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
        + Unique Visitor Variable {#unique-visitor-variable}
          + [Specify the Unique Visitor variable](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
          + [Use case - extracting Visitor IDs](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
        + [Success events](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
        + [Classification Hierarchies](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
        + [List Variables](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
        + [Merchandising eVars](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
      + Marketing Channels {#marketing-channels}
        + [Marketing Channel Manager](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
        + [Marketing Channel Processing Rules](tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)
        + [Marketing Channel Classifications](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
        + [Marketing Channel Expiration](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
      + Traffic Management {#traffic-management}
        + [Overview](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
        + [Schedule Spike](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
        + [Permanent Traffic](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)  
      + [Default Metrics](tools/manage-rs/edit-settings/default-metrics.md)
      + App Management {#app-management}
        + [App Reporting](tools/manage-rs/edit-settings/app-reporting.md)
        + [App Classifications](tools/manage-rs/edit-settings/app-classifications.md)
      + [Media Management](tools/manage-rs/edit-settings/media-management.md)
      + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
      + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
      + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
      + [Privacy Reporting](tools/manage-rs/edit-settings/privacy-reporting.md)
      + Document Cloud Management {#doc-cloud-mgt}
        + [Configure Document Cloud with Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
        + [Configure Document Cloud reporting](tools/manage-rs/edit-settings/document-cloud-config.md)
      + [Advertising Analytics Configuration](tools/manage-rs/edit-settings/advertising-analytics-config.md)
      + Real-Time {#real-time-reports}
        + [Real-time reports overview](tools/manage-rs/edit-settings/realtime/realtime.md)
        + [Real-time reports configuration](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
        + [Supported real-time metrics and dimensions](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
    + [Manage report suites](tools/manage-rs/report-suites-admin.md)
    + [Global report suites](tools/manage-rs/rollup-report-suite.md)
    + [Save a report suite search](tools/manage-rs/t-report-suite-saved-search.md)
    + [Download report suite settings](tools/manage-rs/t-download-rs-settings.md)
    + New report suite {#c-new-report-suite}
      + [Create a report suite](tools/manage-rs/new-rs/t-create-a-report-suite.md)
      + [Create a report suite group](tools/manage-rs/new-rs/t-create-rs-group.md)
      + [New report suite - settings](tools/manage-rs/new-rs/new-report-suite.md)
      + [Settings not copied from a source report suite](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
    + Report suite templates {#report-suite-templates}
      + [Report suite templates overview](tools/manage-rs/rs-templates/report-suite-templates.md)
      + [Aggregator portal](tools/manage-rs/rs-templates/aggregator-portal.md)
      + [Commerce](tools/manage-rs/rs-templates/commerce-admin.md)
      + [Content and Media](tools/manage-rs/rs-templates/content-media.md)
      + [Default template](tools/manage-rs/rs-templates/default-rs-template.md)
      + [Financial Services](tools/manage-rs/rs-templates/financial-services.md)
      + [Job portal](tools/manage-rs/rs-templates/job-portal.md)
      + [Lead Generation](tools/manage-rs/rs-templates/lead-generation.md)
      + [Support Media](tools/manage-rs/rs-templates/support-media.md)
  + Company Settings {#company-settings}
    + [Company Settings overview](tools/company/c-company-settings.md)
    + [Security Manager](tools/company/security-manager.md)
    + [Web Services](tools/company/web-services-admin.md)
    + [Report Builder reports](tools/company/report-builder-reports-admin.md)
    + [Single sign-on](tools/company/single-signon-admin.md)
    + [Hide report suites](tools/company/c-hide-report-suites.md)
    + [Preferences manager](tools/company/preferences-manager.md)
    + [Pending actions](tools/company/pending-actions-admin.md)
    + [Feature access levels](tools/company/feature-access-levels.md)
  + Privacy Labeling {#privacy-labeling}
     + [Overview](tools/privacy-labeling/labeling-overview.md)
     + [Data Privacy labels for Analytics components](tools/privacy-labeling/labels.md)
     + [View/manage report suite's privacy labels](tools/privacy-labeling/view-settings.md)
     + [Labeling best practices](tools/privacy-labeling/best-practices.md)
     + [Labeling example](tools/privacy-labeling/examples.md)
     + [Namespaces](tools/privacy-labeling/namespaces.md)
  + Server Call Usage {#server-call-usage}
    + [Server call usage overview](tools/server-call-usage/overage-overview.md)
    + [View current server call usage](tools/server-call-usage/server-call-usage-dashboard.md)
    + [View report suite usage](tools/server-call-usage/report-suite-usage.md)
    + [Server call usage alerts](tools/server-call-usage/scu-alerts.md)
    + [Server call usage FAQ](tools/server-call-usage/overage-faq.md)
  + User and Product Management (Legacy) {#user-product-management}
    + [User and Product Management (Legacy)](tools/user-management/user-management.md)
    + [Manage legacy user accounts, assets and expirations](tools/user-management/users-assets.md)
    + Migrate users to Adobe Admin Console {#migrate-users}
      + [Analytics User Migration to the Admin Console](tools/user-management/user-migration/c-migration-tool.md)
      + [Migrate Analytics user accounts for Adobe IDs](tools/user-management/user-migration/t-migrate-users.md)
      + [Migrate Analytics user accounts for Enterprise and Federated IDs](tools/user-management/user-migration/migrate-enterprise.md)
      + [Disable legacy logins](tools/user-management/user-migration/t-disable-legacy-login.md)
      + [APIs Affected by the Migration](tools/user-management/user-migration/developer.md)  
+ [Admin API](https://developer.adobe.com/analytics-apis/docs/2.0/)
