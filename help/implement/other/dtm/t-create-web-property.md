---
description: A web property can be any grouping of one or more domains and subdomains with a library of rules, included in one embed code.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Create web property
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
---

# Create web property

A web property can be any grouping of one or more domains and subdomains with a library of rules, included in one embed code.

>[!NOTE]
>
>Only a user with Admin rights can create a property. For more information about roles, see [Create and Manage Groups in DTM](https://docs.adobe.com/content/help/en/dtm/using/admin/groups.html) in the Dynamic Tag Management Product Documentation.

You can manage and track these assets with DTM. For example, suppose that you have multiple websites based on one template and you want to track the same assets on all of these websites. You can apply one web property to multiple domains.

For general information about web properties and best practices, see [Web Properties](https://docs.adobe.com/content/help/en/dtm/using/admin/web-property.html) in the Dynamic Tag Management Product Documentation.

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. Fill in the fields:

    <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Element </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Name</span> </td> 
    <td colname="col2"> <p>The name of your property. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>The base URL of the property. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> This site spans multiple domains </span> </td> 
    <td colname="col2"> <p>You can add and remove domains if you want visitor data to persist between domains. If this option is selected, data for the visit persists across subdomains. </p> <p>This setting lets you specify how you would like to track traffic moving between your associated subdomains or domains. Links to subdomains are treated as outbound links. Visits to subdomains are tracked separately. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Optional) Configure [!UICONTROL Advanced Settings].

    <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Element </th> 
    <th colname="col2" class="entry"> Description </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Allow Multi-Rule Approvals</span> </td> 
    <td colname="col2"> <p>Allows multiple rules for this property to be approved at one time. The default approval allows only single-rule approval. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Enable Selective Publish</span> </td> 
    <td colname="col2"> <p>Specifies whether to allow users to select which approved rules are published. This is the default option. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tracking Cookie Name</span> </td> 
    <td colname="col2"> <p>Overrides the default tracking cookie name. You can customize the name that Dynamic Tag Management uses to track your opt-out status for receiving other cookies. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Tag Timeout</span> </td> 
    <td colname="col2"> <p>Specifies how long Dynamic Tag Management waits for a tag to fire before timing out and cancelling the tag request. </p> <p> Because of how Dynamic Tag Management works, don't worry about this being a high number. DTM has effective methods of ensuring that slow tags do not affect the user experience. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Anchor Delay</span> </td> 
    <td colname="col2"> <p>Specifies how long Dynamic Tag Management waits for tags to fire on clicked links before moving to the next page. The default value is 100 milliseconds. </p> <p>Longer delays improve tracking accuracy. Adobe recommends a delay of 500 milliseconds or less, which the user will not perceive. </p> <p>Dynamic Tag Management will wait up to the time specified, but if the beacon fires sooner, the delay is cut short. (That is, user won't always wait the full length of the delay.) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Click **[!UICONTROL Create Property]**.
