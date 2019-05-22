---
layout: default
title: Getting Started
toc: getting-started-tenant-management
body_color: body-primary
section_name: Getting Started
last_updated: May 9th, 2019
icon_class: icon_documents_alt icon
nextsection_url: /pages/guides/getting-started/authentication
nextsection_label: Authentication
---
# Tenant Management
The Tenant Management API functions allow a user to perform Tenant Security Key administration tasks only.

For Collection and Payout Schemes, Provider Configurations, and other Tenant configuration management, see the appropriate Management documentation on the right.

## Access Requirements
You will need a Tenant Security Key to perform Tenant Management functions.

## Functions
The available functions are:

- Create new Keys
- Get a list of all Keys
- Get a key by its Public Key value
- Delete a Key

## API Documentation
All the Account Management API functions are fully documented in the [Tenant API documentation](https://api-docs.imbursepayments.com/#2db95add-3a76-4424-ada5-fa1fc865011c).

## Models
The following models are used to manage Tenant Security Keys.

### Security Key Model
```json
{
	"accountId": "",
	"tenantId": "",
	"publicKey": "",
	"privateKey": "",
	"roles": []
}
```

Property | Type | Mandatory | Description
-|-
`accountId` | string | Yes | The Id of the Account that owns the Tenant.
`tenantId` | string | No | The Tenant Id this Key belongs to.
`publicKey` | string | Yes | The Public Key portion of the Security Key.
`privateKey` | string | Yes | The Private Key portion of the Security Key.<br/><br/>**<mark>The Private Key value cannot be retrived once created<br/>so it's important this is stored somewhere safe.</mark>**
`roles` | Array of strings | Yes | The roles given to this Key.


**Creating New Keys**<br/>
Creating a new key will return the Private Key value in the response object.

<mark>This Private Key value cannot be retrived again so it's imperitive you store the Private Key value somewhere safe once created.</mark>


**Deleting a Key**<br/>
Deleting a Key will immediately prohibit that keys access to ALL APIS.

<mark>This action cannot be undone.</mark>