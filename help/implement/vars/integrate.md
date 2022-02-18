---
title: Integrate Module
description: The Integrate Module allows Adobe partners to integrate their data collection efforts with your organization.
feature: Variables
exl-id: 378ba77b-be81-49af-8f36-81c65bd01a53
---
# Integrate Module

The Integrate Module allows Adobe partners to integrate their data collection efforts with your organization. This integration provides the opportunity for a two-way data connection. Typically, use of the Integrate Module is driven by an Adobe partner.

>[!NOTE]
>
>Requesting partner data in your implementation can increase delays between page load and data sent to Adobe data collection servers. If a visitor loads a new page before data is sent, that page is not recorded.

## Integrate Module workflow

1. A visitor to your site loads a page that initiates a `get` request for partner data.
2. The Adobe partner receives the `get` request and packages the appropriate variables in a JSON object. The JSON object is returned.
3. Your site receives the JSON object and calls `setVars` to assign the information contained in the JSON object to Adobe Analytics variables
4. An image request is sent to Adobe data collection servers.

## Integrate Module implementation

An organization working with an Adobe partner can use these steps to successfully begin using the Integrate Module.

### Obtain Integrate Module code

Obtaining module code requires a user with Product Admin access, or belonging to a product profile with access to the Code Manager. The method to obtain module code is the same for all implementation methods, including tags in Adobe Experience Platform.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Click the 9-square icon in the upper right, then click the colored Analytics logo.
1. In the top navigation, click **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]**.
1. Download the latest JavaScript AppMeasurement library.
1. Once downloaded, unzip the file and locate `AppMeasurement_Module_Integrate.js`.

### Place the Integrate Module in your implementation

Implementing the Integrate Module on your site requires access to the Data Collection UI in Adobe Experience Platform. If you use a legacy JavaScript implementation, access to your organization's website source code is required.

1. Log in to the [Data Collection UI](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the tag property you intend to edit.
1. Click the Extensions tab, then click Configure under Adobe Analytics.
1. Open the 'Configure tracker using custom code' accordion, then click '</> Open Editor'.
1. Paste the Integrate Module code into the code modal window. Click Save once complete.

## Integrate Module methods

Once the Integrate Module has been implemented, use these methods to configure it to send and receive data from the desired Adobe partner.

### add

The `add` method instantiates a partner object, which serves as an intermediate store of variable data when sharing data between partner systems and your implementation. This method is required for all integrations. A separate partner object must be used for each unique partner if multiple partners are used in a single implementation.

```JavaScript
s.Integrate.add("<partner_name>");
```

Your organization typically works with an Adobe partner to determine the value for partner name.

### beacon

The `beacon` method creates an image request and points it to the specified URL. These image requests are different than standard image requests. The beacon method typically sends data to the Adobe partner instead of Adobe data collection servers.

```JavaScript
p.beacon("<partner_url>/track?qs1=value1&qs2=value2");
```

Your organization typically works with the Adobe partner to determine the value for partner name. Query strings included in the URL are optional, and dependent on partner. The Integrate Module automatically includes a query string containing a random number to prevent browser caching.

### delay

Adobe is working with teams internally to get this method documented.

### get

The `get` method lets a client import partner variables and store them in the partner object. Once data is in the partner object, it can be assigned to Analytics variables and sent in an image request. This method calls a URL, which points to a JSON object containing desired data.

```JavaScript
s.Integrate.<partner_name>.get("<url_to_json_object>?pid=value1&pid2=value2");
```

* **Partner name:** Your organization typically works with the Adobe partner to determine the value for partner name.
* **URL to JSON object:** The URL to a JSON object that contains the partner variables to incorporate into an image request.
* **Query string parameter(s):** Partner account information that identifies your organization in the partner's system. The Adobe partner uses this information to identify your data set.

The Integrate module automatically adds more query strings to the URL. A var query string specifies the name of the JSON object the module expects back from the partner. A random number is also added to prevent browser caching.

### ready

Adobe is working with teams internally to get this method documented.

### useVars

The `useVars` method lets the client share variable values with an Adobe partner.

```JavaScript
s.Integrate.<partner_name>.useVars = function (s,p) {
    p.<partner_var1> = s.eVar1;
    p.<partner_var2> = s.eVar2;
}
```

Your organization typically works with an Adobe partner to determine the values for partner name and the variables that partner uses.

### setVars

The `setVars` method lets the client populate Analytics variables using partner data retrieved. Partner data can be the result of a `get` method, a static assignment, or any other mechanism that populates the partner object with data.

```JavaScript
s.Integrate.<partner_name>.setVars = function (s,p) {
    s.eVar1 = p.<partner_var1>;
    s.eVar2 = p.<partner_var2>;
}
```

Your organization typically works with an Adobe partner to determine the values for partner name and the variables that partner uses.

### script

The `script` method lets an Adobe partner to call additional JavaScript from the partner site if certain conditions are met (for example, if the campaign variable is set).

```JavaScript
p.script("<partner_url>/script?qs1=value1&qs2=value2");
```

Your organization typically works with the Adobe partner to determine the value for partner name. Query strings included in the URL are optional, and dependent on partner. The Integrate Module automatically includes a query string containing a random number to prevent browser caching.
