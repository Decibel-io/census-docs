---
description: >-
  This page walks through how to connect Census with your Google AlloyDB
  database.
---

# Google AlloyDB

## 🏃‍♀️ Getting Started

This guide shows you how to use Census to connect your AlloyDB database to your data warehouse and create your first sync.

{% hint style="info" %}
In order for a third party application (like Census) to query your AlloyDB, Google Cloud requires that you [set up an Auth proxy as detailed in their documentation](https://cloud.google.com/alloydb/docs/auth-proxy/overview). If you have any questions at all setting up this Auth proxy, please reach out to [support@getcensus.com](mailto:support@getcensus.com).&#x20;
{% endhint %}

### Prerequisites

* Have your Census account ready. If you need one, [create a Free Trial Census account](https://app.getcensus.com/) now.
* Have your database credentials ready.
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

### Step 1: Connect AlloyDB

* Once you're in Census, navigate to [Connections](https://app.getcensus.com/connections)
* Click the **Add Service** button
* Select **AlloyDB** in the list

You'll be prompted to put the following credentials into the Census page:

* Hostname
* Port
* Database Name
* Username
* Password

After clicking connect, Census will test the connection that was specified.

![A Green , means you are good to go](<../.gitbook/assets/Screenshot 2022-07-21 at 4.12.30 PM.png>)

After the connection is verified, you all tables will be exposed, but please take a look below on some of the specifics. :arrow\_down:

## 🗄️ Supported Objects <a href="#supported-objects" id="supported-objects"></a>

We support syncing data to Tables in AlloyDB, but they must have a uniqueness constraint on a column. ​

| **Object Name** | **Supported?** |                   **Identifiers**                   |
| :-------------: | :-----------: | :-------------------------------------------------: |
|      Table      |       ✅       | Primary Keys or Columns with Uniqueness Constraints |

## 🔄 Supported Sync Behaviors

{% hint style="info" %}
Learn more about all of our sync behaviors on our [Core Concepts page](../basics/core-concept/#the-different-sync-behaviors).
{% endhint %}

|        **Behaviors** | **Supported?** | **Objects** |
| -------------------: | :------------: | :----------: |
|           **Update** |        ✅       |      All     |
| **Update or Create** |        ✅       |      All     |

[Contact us](mailto:support@getcensus.com) if you want Census to support more Sync behaviors for AlloyDB.

## ❗️Common troubleshooting issues

You may be trying to sync to a table that does not have a uniqueness constraint. If possible, you need to add one to be able to sync to it. The syntax to do so is [here](https://www.postgresql.org/docs/current/ddl-alter.html#DDL-ALTER-ADDING-A-CONSTRAINT).

## 🚑 Need help connecting to Google AlloyDB?

[Contact us](mailto:support@getcensus.com) via support@getcensus.com or start a conversation with us via the [in-app](https://app.getcensus.com) chat.
