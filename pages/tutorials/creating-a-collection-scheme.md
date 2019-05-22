---
layout: default
title: Quickstart Developer Tutorial
toc: tutorial-creating-a-collection-scheme
body_color: body-pink
section_name: Tutorials
last_updated: May 9th, 2019
icon_class: icon_documents_alt icon
---
# Creating a Collection Scheme
If you are need to collect funds from your customer then your Tenant will need at least one Collection Scheme setup. Collection Schemes define the rules around which payment methods, such as Visa, Mastercard, PayPal, etc, are presented to your customers.

For this tutorial we will create a Colection Scheme for a Tenant using the REST API's. 

For more information on Collection Schemes, see the [Collection Schemes in Core Concepts](/pages/guides/core-concepts/#collection-schemes).

## Prerequisites
Aswell as familiarity with the [Core Concepts](/pages/guides/core-concepts), you'll need the following:

- A valid `Management Bearer Token` derived from a `Tenant Security Key`. If you don't have one, see the tutorial [Aquiring a Management Bearer Token](#aquire-management-bearer-token).
- The `appId` of an App you have previously installed that you want to add to this Collection Scheme. If you don't have one, see the tutorial [Installing an Configuring an App](/pages/tutorials/installing-and-configuring-an-app).

# Create a new Collection Scheme
Using the `Management Bearer Token` we can now create a new Collection Scheme.

#### Request

The `name` property can be anything you like in order to help you identify this Collection Scheme later.

The `rules` property is an array of `rule` objects. A Collection Scheme is made up of one or more **Rules**. A Rule describes the **countries**, **currencies**, and **value** range the configured Apps will be valid for.

Within each Rule are **Configurations**. A **Configuration** describes which App is to be used and, optionally, the payment methods that should be excluded from the App.

Rules give you fine grained, flexible control to tune the available payment methods to your customers.

A Collection Scheme can be configured to have many Rules.

You created a Braintree Provider Configuration in the [Creating a Provider Configuration](/pages/tutorials/creating-a-provider-configuration) tutorial.


```curl
curl --location --request POST "https://sandbox-api.imbursepayments.com/v1/schemes/collect" \
  --header "Authorization: Bearer {management-bearer-token}" \
  --header "Content-Type: application/json" \
  --data "{
	\"name\": \"Motor Insurance - EUROPE\",
  "rules": [
    {

    }
  ]
```

#### Response
The `id` property will be the id of your newly created Collection Scheme.

You will need this `id` value in any future operations relating to this Collection Scheme.

```json
{
    "id": "a5b71fa8-3898-4b7e-a19f-9f3d824fabbc",
    "name": "Motor Insurance - EUROPE",
    "paymentProviderConfigurations": ["49800e36-c233-4f18-bebe-1abe535df8b2"],
    "overrides": []
}
```

# What's Next?

- [Create a Collection Scheme](/pages/tutorials/creating-a-collection-scheme)




