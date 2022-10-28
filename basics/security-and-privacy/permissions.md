---
description: >-
  Role-Based Access Controls (RBAC) & Workspaces give Census users the ability
  to control which members of the organization can access information or take
  particular actions.
---

# Permissions

RBAC provides peace of mind, ensuring only those with appropriate permissions can access sensitive user information or take potentially destructive actions with Census Syncs or Census configuration.

{% hint style="info" %}
Role-Based Access Controls are available on Platform plans only. Core plans can create up to two Workspaces.
{% endhint %}

### Organization Administrators

Members of a Census Organization may be promoted to Administrators, which will give them Owner permissions in all [Workspaces](permissions.md#workspaces) and the ability to manage billing, and Organization level settings.

### Workspaces

Census Workspaces allow you to manage permissions granularly for different teams or use-cases. Give your Sales team and your Marketing team their own little slice of Census or keep your staging environment separate from prod. The list of Workspaces in your organization is always visible to all members of your organization, but you can control the level of access for members by assigning them a role.

#### Workspace Roles

Workspace members each have one of four different roles:

* **Owner** – This is the default permission for [Organization Administrators](permissions.md#account-administrators) within a Census Organization. It gives the user access to everything, including managing warehouse & destination connections, API keys, and adding/removing users.&#x20;
* **Editor** – This role grants access to most things in the workspaces including adding and removing connections, in addition to creating and editing syncs and models.&#x20;
* **Operator** – The Operator Role is a special role within Census. It fits between the Editor and Viewer permissions, allowing members with this role to create and edit syncs as long as they're associated with [Broken link](broken-reference "mention") or approved models.
* **Viewer** - The read-only viewer on Census. They can view syncs and segments, and approved models, but cannot modify or take any action within Census.&#x20;

**Access Details**

| Action                                          | Viewer               | Operator             | Editor               | Owner                |
| ----------------------------------------------- | -------------------- | -------------------- | -------------------- | -------------------- |
| View Warehouse Connections                      | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| Create & Manage Warehouse Connections           |                      |                      |                      | :white\_check\_mark: |
| Create & Manage dbt / Looker Connections        |                      |                      |                      | :white\_check\_mark: |
| View Destination Connections                    | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| Create Destination Connections                  |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Manage Destination Connections                  |                      |                      |                      | :white\_check\_mark: |
| Query Approved Models                           | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| Query Non-Approved Models                       |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Create, Edit & Approve Models                   |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Create & Edit Segments                          |                      | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| View Syncs                                      | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| Create, Edit & Run Syncs on Approved Models     |                      | :white\_check\_mark: | :white\_check\_mark: | :white\_check\_mark: |
| Create, Edit & Run Syncs on Non-Approved Models |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Invite new users                                |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Manage member roles                             |                      |                      |                      | :white\_check\_mark: |
| View API Key                                    |                      |                      | :white\_check\_mark: | :white\_check\_mark: |
| Create & Delete API Key                         |                      |                      |                      | :white\_check\_mark: |

#### Creating a Workspace

To get started creating a new Workspace, hit the "Create Workspace" button from your [organization dashboard](https://app.getcensus.com/home). Then simply name your new Workspace, decide whether you wish to give access to your organization or would prefer to keep it restricted, and you're done!

<figure><img src="../../.gitbook/assets/CleanShot 2022-09-30 at 10.44.05@2x (1).png" alt=""><figcaption><p>Creating a new Workspace is easy.</p></figcaption></figure>