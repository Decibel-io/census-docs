---
description: This page describes how to use Census with FullStory
---

# FullStory

## 🏃‍♀️ Getting Started

### 1. Generate a FullStory API Key

In your FullStory account:

1. Navigate to **Settings > Service Accounts**
2. Click **Create key**
3. Hold onto this API Key for the next section, you'll need it!

{% hint style="info" %}
Learn more about FullStory API Keys in their documentation [here](https://help.fullstory.com/hc/en-us/articles/360052021773-Managing-API-Keys).
{% endhint %}

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>Under Settings in FullStory, you can create an API Key</p></figcaption></figure>

### 2. Connect FullStory to Census

* Head back to Census and navigate to [Connections](https://app.getcensus.com/connections).
* Click the Add Service button.
* Select FullStory in the dropdown list.
* Paste your FullStory account's **API Key**. Save your connection and if everything is set up correctly, you should see a successful connection test verifying the connection.

## 🗄 Supported Objects

| **Object Name** | **Supported?** | Identifiers                    |
| --------------: | :------------: | ------------------------------ |
|            User |        ✅       | uid (FullStory User Unique Id) |
|           Event |       🔜       |                                |

[Contact us](mailto:support@getcensus.com) if you want Census to support more objects for FullStory.

## 🔄 Supported Sync Behaviors

{% hint style="info" %}
Learn more about all of our sync behaviors on our [Core Concept page](../basics/core-concept/#the-different-sync-behaviors).
{% endhint %}

|        **Behaviors** | **Supported?** | **Objects** |
| -------------------: | :------------: | :---------: |
|      **Update Only** |        ✅       |     User    |
| **Update or Create** |       🔜       |     User    |
|           **Append** |       🔜       |    Event    |

## 🚑 Need help connecting to FullStory?

[Contact us](mailto:support@getcensus.com) via support@getcensus.com or start a conversation with us via the [in-app](https://app.getcensus.com) chat.
