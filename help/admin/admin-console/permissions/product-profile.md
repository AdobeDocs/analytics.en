# Product profiles in Adobe Analytics

Product profiles are a permission preset that product admins can assign to users within an organization. If you create a product profile and assign an Experience Cloud user to that product profile, they inherit the permission items contained in the product profile.

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## Product profile admins

Product profile admins are an optional group that can add or remove users to that product profile. Note that a product profile admin is not the same as a product admin:

* Product profile admins are merely responsible for the user list of a product profile.
* Product profile admins do not have full access to Adobe Analytics. Full access to Adobe Analytics is reserved for product admins.
* Product profile admins cannot adjust permissions items in their product profile; a product admin must make permission item adjustments.
* Product profile admins are ideal for team leads or managers who simply need to grant and manage access to Adobe Analytics for their team. Individuals would not need to bother system admins or product admins to grant access to Adobe Analytics.

## Adobe Analytics permission items

The minimum required permissions in a product profile to access Adobe Analytics are the following:

* The product profile must have access to at least one report suite
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports & Analytics Access**)

### Report Suites

Grants access to report suites that belong to your Analytics organization. A user must belong to at least one report suite to be given access to use Adobe Analytics.

### Metrics

Grants access to metrics in your report suite. Metrics are listed as their respective component in Analysis Workspace, or if the metric is available in Reports & Analytics, available as a menu item under Site Metrics.

Custom metrics are labeled 'Custom Event 1-1000' to keep them independent of report suites. If 'Custom Event 1' is an enabled permission item, that user has access to event1 in all report suites in the product profile.

### Dimensions

Grants access to dimensions in your report suite. Dimensions are listed as their respective component in Analysis Workspace, or if the dimension is available in Reports & Analytics, available as a menu item.

Custom variables, such as eVars, are labeled 'Custom Conversion 1-250' to keep them independent of report suites. If 'Custom Conversion 1' is an enabled permission item, that user has access to eVar1 in all report suites in the product profile.

### Report Suite Tools

Report suite tools permission items grant access to features that are specific to the report suites the user has access to. See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Analytics Tools

Analytics tools permission items grant access to features that are independent of report suite settings. See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## Product profile developers

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
