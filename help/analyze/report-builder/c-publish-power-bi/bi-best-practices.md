---
description: Power BI best practices.
title: Best practices
uuid: 6d55a9aa-030e-4e4d-963c-ec9cc38e1731
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
---
# Best practices

## Preserve references in Power BI visualizations {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Once you create a request, that request will always have the same reference in Power BI. But if you delete a request, the reference will be used by a new request you create for the same dimension.

If you delete a request in your workbook, make sure you do not have a visualization pointing to that request in Power BI, because otherwise the visualization will break.

* If at all possible, do not delete requests you created in Report Builder 
* Make sure that if you do delete requests on Report Builder, you also delete the corresponding visualization in Power BI.
* If you aren't sure: delete requests you do not need any more, then republish and go to Power BI to see which visualizations have broken
