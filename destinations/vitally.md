---
description: This page describes how to use Census with Vitally.
---

# Vitally

## 🏃‍♀️ Getting Started

In this guide, we will show you how to connect Vitally to Census and create your first sync.

### Prerequisites

* Have your Census account ready. If you need one, [create a Free Trial Census account](https://app.getcensus.com/) now.
* Have your Vitally account ready.
* Have the proper credentials to access to your data source. See our docs for each supported data source for further information:
  * [Azure Synapse](../sources/azure-synapse.md)
  * [Databricks](https://docs.getcensus.com/sources/databricks)
  * [Elasticsearch](https://docs.getcensus.com/sources/elasticsearch)
  * [Google BigQuery](https://docs.getcensus.com/sources/google-bigquery)
  * [Google Sheets](https://docs.getcensus.com/sources/google-sheets)
  * [MySQL](https://docs.getcensus.com/sources/mysql)
  * [Postgres](https://docs.getcensus.com/sources/postgres)
  * [Redshift](https://docs.getcensus.com/sources/redshift)
  * [Rockset](https://docs.getcensus.com/sources/rockset)
  * [Snowflake](https://docs.getcensus.com/sources/snowflake)
  * [SQL Server](https://docs.getcensus.com/sources/sql-server)

### 1. Copy your Vitally API Key(s)

Census makes use of different Vitally APIs for different operations. You're welcome to only connect one or the other, but we suggest connecting both in case you change your mind down the road:

#### **Analytics API**&#x20;

* Required for Update and Create (a.k.a. "Upsert") and Append syncs
* Navigate to `https://[your-domain].vitally.io/integrations/api`
* Select **Integration via HTTPS API**
* Copy the **API Key**

<figure><img src="../.gitbook/assets/vitally1 (1).png" alt=""><figcaption><p>Copy your Analytics API Key from Vitally.</p></figcaption></figure>

#### REST API

* Required for Update Only syncs
* Navigate to `https://[your-domain].vitally.io/integrations/public-api`
* Copy the part of **Basic Auth Header** after the word `Basic` (e.g. if it reads `Basic 1234`, then only copy `1234`)

<figure><img src="../.gitbook/assets/vitally2.png" alt=""><figcaption><p>Copy your REST API Key from Vitally.</p></figcaption></figure>

### 2. Connect Vitally

* Return to Census and navigate to the **Connections** page
* Click the **Add Service** button
* Select **Vitally** from the list
* Paste your API Key(s) into the relevant fields
* Optionally name your new connection and then click **Connect**

## 🗄 Supported Objects

| **Object Name** | **Supported?** |   **Matching Keys**   | **Create Fields** |
| --------------: | :------------: | :-------------------: | :---------------: |
|            User |        ✅       |        User ID        |         ✅         |
|         Account |        ✅       |       Account ID      |         ✅         |
|    Organization |        ✅       |    Organization ID    |         ✅         |
|     Track Event |        ✅       | Any unique identifier |         ✅         |
|             NPS |       🔜       |           -           |         -         |

Vitally defines User ID and Account ID as the unique identifier for these objects in your system. You are free to use whatever ID you like, but it needs to be unique.

### User Behavior Notes

* Users must have at least one Account in Vitally so **Accounts** is a required field when syncing to users. It's also an Array field so you'll need to provide it an array value or JSON formatted Array.
* Any Account ID values that don't already exist in Vitally will be automatically created.

![](<../.gitbook/assets/Screen Shot 2022-06-30 at 6.50.03 PM.png>)

## 🔄 Supported Sync Behaviors

{% hint style="info" %}
Learn more about all of our sync behaviors on our [Core Concept page](../basics/core-concept/#the-different-sync-behaviors).
{% endhint %}

<table data-header-hidden><thead><tr><th align="right"></th><th width="197.33333333333331" align="center"></th><th align="center"></th></tr></thead><tbody><tr><td align="right"><strong>Behaviors</strong></td><td align="center"><strong>Supported?</strong></td><td align="center"><strong>Objects</strong></td></tr><tr><td align="right"><strong>Update or Create</strong></td><td align="center">✅</td><td align="center">Account, User, Organization</td></tr><tr><td align="right"><strong>Update Only</strong></td><td align="center">✅</td><td align="center">Account, User, Organization</td></tr><tr><td align="right"><strong>Append</strong></td><td align="center">✅</td><td align="center">Track Event</td></tr></tbody></table>

[Contact us](mailto:support@getcensus.com) if you want Census to support more sync behaviors for Vitally.

## 🔍 Additional Service Quirks

* Vitally's internal database has a delay between Census completing its upload and having those results reflected in the UI. This delay can be several seconds to several minutes in extreme cases.
* As with all Census syncs, when you unmap a field in Census, we will stop updating those fields. We do not delete them.

## 🚑 Need help connecting to Vitally?

[Contact us](mailto:support@getcensus.com) via support@getcensus.com or start a conversation with us via the [in-app](https://app.getcensus.com) chat.
