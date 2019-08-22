---
description: To activate the integration you must complete the Qualtrics integration wizard within the Data Connectors interface
seo-description: To activate the integration you must complete the Qualtrics integration wizard within the Data Connectors interface
seo-title: Completing the Adobe Integration Wizard
solution: Analytics
subtopic: Qualtrics
title: Completing the Adobe Integration Wizard
topic: Data connectors
uuid: e065fba4-1fe1-4e25-9c45-6c52dc20f81e
index: y
internal: n
snippet: y
---

# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

To activate the integration you must complete the Qualtrics integration wizard within the Data Connectors interface

1. Navigate to data connectors and launch the Qualtrics integration wizard. ([Data Connectors Help](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. Select the report suite that you want to use for this integration and provide a name.

   Complete the integration wizard, providing the information described in the following steps. 1. **Wizard Step 1**

   |  Email Address  | The primary contact email address.  |
   |---|---|
   |  Description  | (Optional) Description for this integration setup.  |
   |  Qualtrics Organization ID  | [Looking up your Qualtrics Organization ID](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96)  |
   |  Adobe SiteCatalyst Token  | [Generating your Qualtrics Adobe Analytics Token](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372)  |

1. **Wizard Step 2 - Variable Mappings **

   |  Qualtrics Response List  | Select an available list variable from your report suite. (You may need to enable a new listVar within the Report Suite Manager.)  |
   |---|---|
   |  Qualtrics Response ID  | Select an available eVar or prop from your report suite. (You may need to enable a new listVar within the Report Suite Manager.)  |
   |  Tracking Server  |Provide the tracking server (domain) setting that you use to track Adobe Analytics data. Use the `trackingServerSecure` tracking server if it differs from your standard tracking server setting.  |
   |  Qualtrics Survey Submissions  | Select an available event from your report suite (you may need to enable a new event from within the Report Suite Manager).  |

1. **Wizard Step 3**: Nothing required, informational only.

   Step Result 1. **Wizard Step 4 - Export Settings **

   |  eVar  | Select up to five of your eVars to expose for exporting to Qualtrics  |
   |---|---|
   |  Events  | Select up to five of your custom events to expose for exporting to Qualtrics  |
   |  Props  | Select up to five of your Props to expose for exporting to Qualtrics  |
   |  Access Requests  |Check the box for any of the standard metrics and dimensions that you wish to export to Qualtrics. The `visitor_id` is required to allow the export to function properly.  |

1. **Wizard Step 5**: Review configuration and then click **[!UICONTROL Activate Now]**.
