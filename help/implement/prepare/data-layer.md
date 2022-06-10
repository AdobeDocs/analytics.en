---
title: Create a data layer
description: Learn what a data layer is in your Analytics implementation, and how it can be used to map variables in Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
---
# Create a data layer

A data layer is a framework of JavaScript objects on your site that contains all variable values used in your implementation. It allows greater control and easier maintenance in your implementation.

Here is a video on using data layers:

>[!VIDEO](https://video.tv.adobe.com/v/28775/?quality=12)

## Prerequisites

[Create a solution design document](solution-design.md) - It is important for your organization to align on tracking requirements. Make sure that you are prepared with a solution design document before approaching development teams in your organization.

## Workflow

Implementing Adobe Analytics using a data layer typically follows these steps:

1. **Work with your site development team to implement a data layer**: Your site development team is primarily responsible for making sure the data layer object populates with correct values. Review this page with your site development team to make sure expectations are aligned between teams.

   >[!NOTE]
   >
   >Following Adobe's recommended data layer specifications is optional. If you already have a data layer, or otherwise choose not to follow Adobe's specifications, make sure that your organization aligns on what specification to follow.
1. **Validate your data layer using a browser console**: Once a data layer is created, you can validate that it is working using any browser's developer console. You can open the developer console in most browsers using the `F12` key. An example variable value would be `digitalData.page.pageInfo.pageID`.
1. **Use Adobe Experience Platform Data Collection to map data layer objects to data elements**: Create data elements in Adobe Experience Platform Data Collection, and map them to the JavaScript attributes outlined in your data layer.
1. **Use the Adobe Analytics tag extension to map data elements to Analytics variables**: Following your solution design document, assign each data element to the appropriate Analytics variable.

## Specifications

Adobe recommends following the [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) outlined by the [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/). Use the following sections to understand how data layer elements interact with Adobe Analytics.

The recommended overarching data layer object to use is `digitalData`. The following example lists a somewhat comprehensive data layer JSON object with example values:

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

Use the [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) report for details on each object and sub-object. Not all sites use all objects; for example, if you host a news site, it is unlikely that you have use for the `digitalData.product` object array.

Data layers are extensible; if you have requirements specific to your organization, you can include objects in your data layer to accommodate those needs.

## Setting data layer values

Data layers typically generate server-side, referencing the same objects used to build the site content. Establish the site's data layer based on tracking requirements set in your organization's [solution design document](solution-design.md).

## Next steps

[Map data layer objects to data elements](../launch/layer-to-elements.md): Use your site's data layer in Adobe Experience Platform.
