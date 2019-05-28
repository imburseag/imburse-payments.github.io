---
layout: default
title: Quickstart Developer Tutorial
toc: get-payout-bearer-token
body_color: body-pink
section_name: Tutorials
last_updated: May 9th, 2019
icon_class: icon_documents_alt icon
---
# Get a Payout Bearer Token
This tutorial will take you through getting a Payout Bearer Token using a Tenant Security Key.

# Prerequisites
Aswell as familiarity with the [Core Concepts](/pages/guides/core-concepts), you'll need the following:

- Familiar with creating an HMAC token using a Security Key.
- A `Tenant Security Key`. See the tutorial [Creating a Tenant Security Key](/pages/tutorials/creating-a-tenant-security-key) here if you need to create one.

# Get Payout Bearer Token
You will need to generate an HMAC token for the following following request using a `Tenant Security Key`.

**Note: If you already have a valid `Payout Bearer Token` derived from a `Tenant Security Key` then you can skip this tutorial. Use your existing `Payout Bearer Token` rather than creating a new one. You don't have to create a new `Payout Bearer Token` for each request.**


#### Request
Replace the `{hmac-token}` placeholder value with your actual HMAC token.

```curl
curl --location --request POST "https://sandbox-api.imbursepayments.com/identity/v1/hmac/payout" \
  --header "Authorization: Hmac {hmac-token}"
```

#### Response
The `Payout Bearer Token` will be contained in the `accessToken` property of the response body:

```json
{
    "accessToken": "",
    "expires": ""
}
```

# What's Next?

- [Processing a Payout Instruction](/pages/tutorials/processing-a-payout-instruction)
