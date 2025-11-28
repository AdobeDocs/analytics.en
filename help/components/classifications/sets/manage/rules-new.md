---
title: Classification Sets Rules
description: Learn how to use classification sets rules to define rules for classification data.
feature: Classifications
hide: yes
hidefromtoc: yes
---

# Classification sets rules

You use rules to support automatic classifications in scenarios where your key dimension is constantly changing. The update of classifications through upload or automation becomes a cumbersome process or lags proper classification for new dimension values. For example, internal campaigns, tracking codes, or product SKUs. The dimension must contain values that allow you to apply one or more rules so you can derive classification data from the values.

You define rules within the context of a classification set, which implies that rules are applied (when activated) to all report suite and key dimension combinations that are subscribed to the classification set. This implementation is somewhat different from how the legacy Classification rule builder works. In the Classification rule bulder you define one or more rules as part of a rule set separately and then associate the rule set with one or more report suites. In the new interface, the rules within the classification set are also referred to as rule set but are defined within the same interface where you configure other classification set attributes.


To define a rule set for a classification set:

1. Select **[!UICONTROL Components]** from the Adobe Analytics top menu bar, then select **[!UICONTROL Classification sets]**.
1. In **[!UICONTROL Classification Sets]**, select the **[!UICONTROL Classification Sets]** tab.
1. In the **[!UICONTROL Classifications Sets]** manager, select the classification set for which you want to define the rules.
1. In the **[!UICONTROL Classification Set: _classification set name_]** dialog, select the **[!UICONTROL Rules]** tab. 

   * If you are accessing the **[!UICONTROL Rules]** interface for the first time for a classification set, or you decided so far to continue to use the legacy rules builder interface, you are presented with a dialog that allows you to select how to get started. The options are:

     * **Migrate existing rules**. Import your current classification rules and continue to work with these rules in the new interface. Your existing rules will be preserved and converted to the new format. 
       * Select **[!UICONTROL Migrate rules]** to continue.
       * In the **[!UICONTROL Confirm migration]** dialog, read the implications of the migration.
         * Select **[!UICONTROL Migrate rules]** to confirm the migration. After the migration is completed, use the Rule set interface to create new rules and edit your existing migrated rules.
         * Select **[!UICONTROL Cancel]** to cancel the migration
       
     * **Start fresh**. Create new classification rules from scratch using the new rule builder. Select this option if you want to redesign your classification logic or start fresh with new classification rules. 
       * Select **[!UICONTROL Create new rules]** to continue.
       * In the **[!UICONTROL Confirm start fresh]** dialog, read the implications of a fresh start.
         * Select **[!UICONTROL Start fresh]** to confim a fresh start and discard any existing rules. Use the Rule set interface to create new rules.
         * Select **[!UICONTROL Cancel]** to cancel.


     * **Use legacy interface**. Continue to use the previous rule builder interface. You can migrate to the new experience at any time when you're ready. 
       * Select **[!UICONTROL Go to legacy interface]** to continue. You are directed to the legacy **[!UICONTROL Classification Rule Builder]** interface.

   * If you already have migrated rules or created new rules for a classification set, you end up directly in the Rule set interface. 



## Rule set interface

When you create or edit rules, you use the Rule set interface.

![Rule set interface](assets/rulesets-ui.png)

| | Name | Description |
|---|---|---|
| 1 | **[!UICONTROL Functions]** | You use the Function area to select and drag and drop your functions to the rule set builder. |
| 2 | **Rule set builder** | You build your rule set using one or more rules. A rule is the implementation of a function and always associated with only one one function. A function can have multiple operators. You create a rule by dragging and dropping a function into the rule set builder. The function type defines the interface of the rule. <br/>See the [Rule interface](#rule-interface) for more information.<br/>You can insert functions at any place, and the functions are executed in sequence to determine the final values for the classifications.<br/>Use **[!UICONTROL Collapse all]** to collapse all rules and use **[!UICONTROL Expand all]** to expand all rules. | 
| 3 | **[!UICONTROL Status]** | Shows the status and last modified date of the rule set. Select **[!UICONTROL Activate]** to activate the rule set. Select **[!UICONTROL Deactivate]** to deactivate the rule set. |
| 4 | **[!UICONTROL Lookback]** | Specify the lookback window for the rule set. You can select an option (from 1 month to 6 months) from the drop-down menu. Select **[!UICONTROL Perform lookback]** to perform a lookback using the selected lookback period. |
| 5 | **[!UICONTROL Test options]** | Use sample key dimension values to test the classifications. Add or paste values in the Sample keys text area. Select Remember sample keys to ensure sample keys are available once you return to the rule set interface. Select Test rule set to test your rule set. |


## Rule interface

