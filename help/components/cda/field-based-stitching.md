---
title: Field-based stitching
description: Understand the prerequisites and limitations of stitching data using field-based stitching.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
---
# Field-based stitching

Cross-Device Analytics provides two distinct methods to stitch data together. This method relies on an Analytics variable, such as a [prop](/help/implement/vars/page-vars/prop.md) or [eVar](/help/implement/vars/page-vars/evar.md), to contain a person identifier. It uses that variable as a base to link devices together.

## Prerequisites specific to field-based stitching

If you intend to implement Cross-Device Analytics using field-based stitching, the following are required. Work with teams within your organization and your Adobe Account Manager to ensure that you meet all of the following.

>[!IMPORTANT]
>
>Failure to meet all prerequisites can result in the inability to enable Cross-Device Analytics or poor results when stitching data.

* All prerequisites listed on the [overview page](overview.md).
* Your implementation must set a prop or eVar that uniquely identifies an individual whenever possible, such as when a user logs in or opens an email. This requirement applies to all platforms, including mobile apps if used. Communicate the desired identifying variable to your Account Manager when provisioned for Field-based stitching.

## Limitations specific to field-based stitching

* Field-based stitching works best on report suites that have a high user identification/authentication rate.
* Although props and eVars each have rules for how upper and lowercase characters are handled for reporting purposes, field-based stitching does not transform the prop or eVar used for stitching in any manner. Field-based stitching uses the value in the specified field as it exists post VISTA rules and post processing rules. The stitching process is case-sensitive. For example, if sometimes the word 'Bob' appears in the prop/eVar, and sometimes the word 'BOB' appears, these will be treated as two separate people by the stitching process.
* Given that field-based stitching is case-sensitive, Adobe recommends reviewing any VISTA rules or processing rules that apply to the prop or eVar being used for field-based stitching. They need to be reviewed to ensure that none of these rules are introducing new forms of the same ID. For example, you should ensure that no VISTA or processing rules are introducing lowercasing to the prop or eVar on only a portion of the hits.
* Field-based stitching does not support use of more than one prop or eVar for stitching purposes. For example, if eVar12 contains login ID and eVar20 contains email ID, you must choose one of them.
* Field-based stitching does not combine or concatenate fields (e.g. eVar10 + prop5). 
* The prop or eVar should contain a single type of ID. For instance, the prop or eVar should not contain a combination of login IDs and email IDs.
* If multiple hits occur with the same timestamp for the same visitor, but with different values in the stitching prop or eVar, CDA will choose based on alphabetical order. So if visitor A has two hits with the same timestamp and one of the hits specifies Bob and the other specifies Ann, CDA will choose Ann.


## Next steps

Once your organization meets all requirements and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).
