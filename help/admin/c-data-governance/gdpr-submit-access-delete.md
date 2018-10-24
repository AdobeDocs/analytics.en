---
description: null
seo-description: null
seo-title: Submit Access and Delete Requests
title: Submit Access and Delete Requests
uuid: b30669c1-2986-4abb-bb50-f182d3229ead
index: y
internal: n
snippet: y
---

# Submit Access and Delete Requests

>[!NOTE]
>
>This page describes functionality that will be available at a later date.

* [Overview](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_BD70882995894C1CA19C205C49FEC23C) 
* [Manage Consumer Consent](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_3012015E7E8942519FB9279CF7057EAB) 
* [Validate Users and Their Data](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_AFB2CC225AA94AF6A3CE9F24EF788358) 
* [Submit Requests](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_F70F4D91B7FF4242876338A66D2125C3) 
* [Sample JSON Request](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_DB9DE6492FE740918F91D413E7BAB88F) 
* [Response Times](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_93F554F65DBB48A18B75EB5784056C96) 
* [Testing GDPR Processing on Your Data](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_FBA843DBFAE64D979D8DB8A3C56784D7)

## Overview {#section_BD70882995894C1CA19C205C49FEC23C}

If your customers (consumers/data subjects) want to know what data you maintain about them or decide they want to be deleted from your Analytics properties, you as the data controller are responsible for responding to those requests. The data controller determines how your organization will interact with data subjects (e.g., through a data subject user portal) and manages interactions with the data subject. It also is the controller's responsibility to close the loop with the data subject when the request is fulfilled. In other words, Adobe Experience Cloud, as the data processor, will not accept requests directly from data subjects or return data directly to them. Rather, Adobe will receive requests from and return data to only you as the data controller.

You also may want to ensure your mobile apps and websites will have relevant pop-up notices and supporting materials about data subjects' rights regarding their directly identifiable or indirectly identifiable data, and other data you collect.

## Manage Consumer Consent {#section_3012015E7E8942519FB9279CF7057EAB}

You, as the data controller, are responsible for obtaining explicit consent from your data subjects before you collect data about them (possibly including Adobe Analytics data) and for [implementing an opt-out mechanism](https://marketing.adobe.com/resources/help/en_US/dtm/opt-in.html) on your web site. This lets your data subjects opt out of future Adobe Experience Cloud data collection.

## Validate Users and Their Data {#section_AFB2CC225AA94AF6A3CE9F24EF788358}

You, as the data controller, are responsible for verifying that the data subject is who they say they are and that they have a right to the data they are requesting. Further, it is your responsibility to ensure that the correct data is returned to the data subject and that they don’t inadvertently receive data about other data subjects.

This includes reviewing the data returned by Adobe Analytics as part of a GDPR access request before sending it on to the data subject. Particular care should be taken if you are using Person IDs, and returning not only data where that ID is present, but also data for other hits on a shared device where that ID was sometimes present ( [ID Expansion](../../admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913)).

Each file combines data from all your report suites, automatically removing extra copies of replicated hits. You can decide which of these files to return to the data subject. Or you may extract some of this data and combine with data from other systems before returning it to the data subject.

## Submit Requests {#section_F70F4D91B7FF4242876338A66D2125C3}

You can submit GDPR access and delete requests through our [GDPR UI portal](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) or via our [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md).

>[!NOTE]
>
>The GDPR API supports batch submissions for multiple users in a single request. The currently supported limit is 1000 separate users (may have multiple IDs per user) in a single request JSON file.

## Sample JSON Request {#section_DB9DE6492FE740918F91D413E7BAB88F}

Here is the JSON that might be submitted through the GDPR API or UI, requesting GDPR processing for three users.

```
{ 
    "companyContexts": [ 
        { 
            "namespace": "imsOrgID", 
            "value": "5D7236525AA6D9580A495C6C@AdobeOrg" 
        } 
    ], 
    "users": [ 
        { 
            "key": "GDPR-1234", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "AAID", 
                    "namespaceId", 10, 
                    "type": "standard", 
                    "description": "Legacy Visitor ID", 
                    "value": "2D783E5885312539-4000010360000181", 
                } 
            ] 
        }, 
        { 
            "key": "GDPR-1235", 
            "action": ["access"], 
            "userIDs": [ 
                { 
                    "namespace": "ECID", 
                    "namespaceId": 4, 
                    "type": "standard", 
                    "description": "This is the ID generated by the Adobe ID service.", 
                    "value": "22470866493385587460528148368265592748", 
                } 
            ] 
        }, 
        { 
            "key": "GDPR-1236", 
            "action": ["access","delete"], 
            "userIDs": [ 
                { 
                    "namespace": "CRM-ID", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar17 in some report suites", 
                    "value": "ACME-12345678", 
                }, 
                { 
                    "namespace": "email address", 
                    "type": "analytics", 
                    "description": "namespace defined on eVar23 in some report suites", 
                    "value": "john@mail.com", 
                } 
            ] 
        } 
    ], 
    "expandIds": true 
} 

```

Notice there are three blocks in the user’s section, representing three separate requests, presumably for three separate data subjects.

* The first request is an access request using a traditional Adobe Analytics cookie ID (AAID). 
* The second request is also an access request but is using an MCID/ECID cookie. 
* The third request is requesting both access and delete for the specified IDs. While ID Expansion is specified for all of the requests, it will have the biggest impact on this third request, as it is the only one that uses non-cookie IDs. As a result, this request will also discover cookie IDs associated with any devices with the specified CRM-ID or email address, and expand the request to include those IDs as well.

Keep in mind that

* The value “5D7236525AA6D9580A495C6C@AdobeOrg” in the “companyContexts” section must be updated with the value of your own Experience Cloud (IMS) Org. 
* The “type” and “namespace” fields are described in more detail in the [Namespaces](../../admin/c-data-governance/gdpr-namespaces.md#concept_26C6392D92194BC1BA3986A144AF285D) section. 
* The “description” fields are ignored. 
* The “key” fields can contain any value that you want. If you have an internal ID that you are using for tracking GDPR requests, you could place that value here, to make it easier to match requests in Adobe’s system to those in your own systems.

## Response Details {#section_93F554F65DBB48A18B75EB5784056C96}

This sections contains details on access and delete responses.

**Access Response Details**

The data returned for an access request provides you, the data controller, with a URL you can use to download a ZIP file containing a directory for each Adobe product you own. Within the Analytics folder, there may be:

* Person Files - Derived from hits containing a matched ID-PERSON label

    * A .CSV file with one row for every matching hit, and one column for every field with an ACC-ALL or ACC-PERSON label, sorted by timestamp. 
    * An HTML summary file with one entry for every ACC-ALL or ACC-PERSON label. Each entry lists all unique values for that field and the number of times each occurred. Fields containing timestamps are rounded to specify only unique days.

* Device Files - Derived from hits where one of the fields matched a specified ID-DEVICE but none matched a specified ID-PERSON

    * A .CSV file with one row for every matching hit, and one column for every field with an ACC-ALL label, sorted by timestamp. 
    * HTML summary file with one entry for every ACC-ALL label. Each entry will list all unique values for that field and the number of times each occurred. Fields containing timestamps are rounded to specify only unique days.

Each file combines data from all your report suites, automatically removing extra copies of replicated hits.

You can decide which of these to return to the data subject. Or you may extract some of this data and combine with data from other systems before returning it to the data subject.

**Delete Response Details**

No data is returned for delete requests - only a status to the GDPR API that the request was completed successfully.

## Testing GDPR Processing on Your Data {#section_FBA843DBFAE64D979D8DB8A3C56784D7}

Typically, Analytics customers will set up some test report suites to verify functionality before it is released to the general public. Pre-production websites or apps will send data into these test/dev/QA report suites to evaluate how things will work when the code releases before real traffic is sent to the production report suites.

However, with a normal configuration, GPDR request processing cannot be tested first on these test report suites, before applying requests to production report suites. The reason for this is that a GDPR request is automatically applied to all report suites in the IMS Org, which is often all report suites for your company.

There are a few ways that you can still test your GDPR processing prior to applying it to all your report suites:

* One option is to set up a separate IMS Org that contains only test report suites. Then use this IMS Org for your GDPR testing and your normal IMS Org for actual GDPR processing. 
* Another option is to assign different namespaces to the IDs in your test report suites, versus those in your production report suites.

  For example, you can prefix each namespace with “qa-“ in your test report suites. When you submit GDPR requests with only namespaces with the qa prefix, these requests will only run against your test report suites. Later, when you submit requests without the qa prefix, they will apply to your production report suites. **This is the recommended approach, unless you use the visitorId, AAID, ECID or customVisitorId namespaces, because these are hardcoded and you cannot specify alternate names for them in your test report suites**.

