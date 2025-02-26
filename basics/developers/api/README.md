---
description: >-
  This page describes how to use the Management API to manage your connections
  and syncs.
---

# Management API

The Management API lets you integrate core bits of Census's functionality right into your workflows. You can view information about your connections and syncs, as well as create and trigger syncs. Each endpoint returns a status field and either a data object or a single value providing context on what was requested.

Tables that include **Response Property** detail the results of the entire response. Tables that include **Data Property** detail the returned data housed in the top level `data` attribute of the response. Tables that include **Attributes** detail relevant bits of info for nested objects used in requests.

## Postman Collection <img src="../../../.gitbook/assets/postman-icon-svgrepo-com.svg" alt="" data-size="line">

Census has a Postman Collection that encompasses all API endpoints that Census offers.  Whether you are looking to quickly test out our API or trying to build custom authentication flows into your application, the Census Postman Collection will help expedite those projects.

Check out our Postman Collection [here](https://www.postman.com/getcensus/workspace/census-api/overview)!

## Getting API Access

Each Census Workspace has its own API key. You can access it within the **Settings** page.

<figure><img src="../../../.gitbook/assets/CleanShot 2022-10-24 at 11.46.55@2x.png" alt=""><figcaption></figcaption></figure>

## Authenticating API Requests

The Census API uses basic authentication to provide API credentials. When accessing the Census API, provide the following credentials using your client library or preferred tool:

| Username | `bearer`        |
| -------- | --------------- |
| Password | \<Your API Key> |

{% hint style="info" %}
If using a tool to make requests, please make sure to include this in your Headers:

`Accept */*`
{% endhint %}
