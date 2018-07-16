Launch by Adobe is the tool you can use to integrate the Experience Cloud solutions on your website. This guide outlines specifically how a Launch admin can get a basic Adobe Analytics implementation configured correctly.

# Prerequisites
[Create a report suite](create-report-suite.md): Create a silo for Analytics data to be collected

# Create a property and install vital extensions
Properties are overarching containers you use to manage tags. Extensions let you install product-specific tags and configure them.

1. Go to Launch by Adobe and log in if prompted.
2. Click 'New Property'.
3. Give your Property a name, such as the title of your website, and enter the domain you intend to implement Analytics on. Click Save.
4. Click your newly created property to enter its settings.
5. Click the Extensions tab, then click Catalog.
6. Locate Experience Cloud ID Service, then click Install.
7. All settings, including Experience Cloud Organization ID, should be already filled out. Click Save.
8. Back in the extensions catalog, locate Adobe Analytics and click Install.

# Create data elements for Adobe Analytics
Data elements are references to specific parts of your site to collect variable values.
1. Go to [Launch by Adobe](https://launch.adobe.com) and log in if prompted.
2. Click the Launch property that you intend to implement on your site.
3. Click the Data Elements tab, then click Create New Data Element.
4. Give the data element the following settings:
   - Name: Page Name
   - Extension: Core
   - Data Element Type: JavaScript Variable
   - Path to variable: window.document.title
   - Clean text checked
   - Duration: Pageview
5. Click Save.
 

# Create rules for Adobe Analytics
Rules map data elements to Analytics variable values, and determine when those values are sent to Adobe's servers.

1. Go to [Launch by Adobe](https://launch.adobe.com) and log in if prompted.
2. Click the Launch property that you intend to implement on your site.
3. Click Create New Rule and name it Global Rule.
4. Click Add next to events, and enter the following settings:
   - Extension: Core
   - Event Type: Library Loaded (Page Top)
   - Name: Core - Library Loaded (Page Top)
   - Order: 50
5. Click Keep Changes.
6. Under Actions, click Add, and enter the following settings:
   - Extension: Adobe Analytics
   - Action Type: Set Variables
   - Page Name: click the container icon, and select the Page Name data element.
   - Campaign: Query parameter with a value of cid
7. Click Keep Changes.
8. Click the Plus sign next to actions to add another action, and enter the following settings:
   - Extension: Adobe Analytics
   - Action Type: Send Beacon
   - Name: Adobe Analytics - Send Beacon
   - Tracking: s.t()
9. Click Keep Changes.
10. Verify that you have the event and two actions set, then click Save.

# Documentation and additional resources
- [Getting Started with Launch](https://docs.adobelaunch.com/getting-started): Full documentation for Launch, including a more in-depth getting started guide
- [Launch, by Adobe's YouTube channel](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd) 

# Next steps
- [Deploy your Analytics implementation to your dev environment](deploy-dev.md): Get Analytics code working in a test environment.