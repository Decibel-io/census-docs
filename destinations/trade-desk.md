---
description: This page describes how to use Census with Trade Desk.
---

# Trade Desk

## 🏃‍♀️ Getting Started

1. Click **Add Service**.
2. Select **Trade Desk** from the menu.
3. If you plan to sync ad groups and/or campaigns, enter your **API Token**. If you plan to sync conversion events, enter your **Postback URL**. Contact your Trade Desk account manager if you don't know what this is.

<figure><img src="../.gitbook/assets/tradedesk.png" alt=""><figcaption><p>Generate an API Token from the Trade Desk developer portal.</p></figcaption></figure>

## 🔀 Supported Objects and Behaviors

|          **Object Name** | **Supported?** | **Identifiers**       | **Behaviors**       |
| -----------------------: | :------------: | --------------------- | ------------------- |
|                 Ad Group |        ✅       | Any unique identifier | Update Only, Append |
|               Advertiser |        ✅       | Any unique identifier | Update Only, Append |
|                 Campaign |        ✅       | Any unique identifier | Update Only, Append |
|         Conversion Event |        ✅       | Any unique identifier | Append              |
|             Tracking Tag |        ✅       | Any unique identifier | Update Only, Append |
| First-Party Data Segment |       🔜       |                       |                     |
|         CRM Data Segment |       🔜       |                       |                     |

[Contact us](mailto:support@getcensus.com) if you want Census to support more Trade Desk objects and/or behaviors.

## 🚑 Need help connecting to Trade Desk?

[Contact us](mailto:support@getcensus.com) via support@getcensus.com or start a conversation with us via the [in-app](https://app.getcensus.com) chat.
