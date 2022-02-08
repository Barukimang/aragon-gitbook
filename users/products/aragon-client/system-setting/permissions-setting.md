---
cover: ../../../../.gitbook/assets/03.png
coverY: 0
---

# Permissions Setting

The Permissions app is used to view all of the current permissions that have been set in an organization and add or remove permissions as needed. The permissions set by the Permissions app define which entities have what permissions to perform various actions in an organization. For example, any account may have permission to create a vote but only tokenholders in an organization may have permission to cast a vote.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a697f2c7d3a7e9ae19121/file-gDcISkpUXb.png)

## <mark style="color:purple;">**3.5.1 Browse by app**</mark>

The Permissions app shows a list of every app installed in the organization and the address or token symbol of that app. You can change App permissions and System permissions.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a562c7d3a7e9ae1912e/file-0y5pgj1j2k.png)

![](../../../../.gitbook/assets/file-mnVytX0QZA.png)

Every app has a list of actions that can be performed on the app, a list of actions that other entities have been given permission to perform on the app, and a list of permissions that the app has been granted.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6a7104286364bc8f8145/file-NKD9Oqrl0V.png)

### **3.5.1.1 Available permissions**

The “Available permissions” section shows what actions can be performed on the app, what entity has permission to perform each action, and which entity manages each action. This entity is called a “manager”.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b052c7d3a7e9ae19132/file-68mYNPchqp.png)

A manager has the ability to choose which entities have permission to perform an action and the ability to change the manager of that action. If a manager removes themselves as a manager of a permission without re-assigning the manager role to another entity, then management of that action defaults to whichever entity manages the “Create permissions” action in the ACL app. If the manager of an action is set as `0x0000000000000000000000000000000000000001` then no new manager can be set and permissions granted for that action will be locked forever.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b1904286364bc8f814d/file-UNomybgFUB.png)

If an action has not been given a manager yet, then it must be initialized. To initialize an action, enter the address of the entity that you want to manage the action, select which entity you want to grant permission to perform the action, then click the “Initialize permission” button to initialize the permission, if you have permission to do so.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b2304286364bc8f814f/file-fna5oPikEA.png)

## <mark style="color:purple;">**3.5.2 Browse by entity**</mark>

Back on the main Permissions page, you have the ability to get an at-a-glance view of all of the permissions set in an organization in the “Browse by entity” section. Here, you can quickly see which entities have been granted permission to perform which actions in the organization. Clicking “View details” will take you to the permissions page for that entity.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b6104286364bc8f8153/file-W609vjv1Pi.png)

## <mark style="color:purple;">**3.5.3 Add permission**</mark>

To give permission to an entity to perform an action on an app, click the “Add permission” button, select which app you want the entity to perform the action on, select which entity you want to grant the permission to, then select the action you want to grant the entity permission to perform.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a6b732c7d3a7e9ae1913a/file-xsxDomUDSy.png)

Each app has different actions that an entity can be granted permission to perform. Granting permission to an entity to perform these actions on these apps will allow them to:

### **ACL**

* Create permissions: create permissions that have not been initialized yet in any app that uses this ACL instance `*`

`*` _These actions are very sensitive actions that will give the entity with permission to perform these actions almost complete control of your organization._

### **EVM Script Registry**

* Add executors: add an executor to the organization`*`
* Enable and disable executors: enable and disable executors in an organization`*`

_Note: An executor is an interpreter for running scripts in an organization. All of the apps in an organization use the executors in the organization to execute scripts that are part of transactions sent to the app. Each script has an identifier that determines which executor is used for running the script. For example, whenever a vote transaction is sent to the Voting app, the app runs a script, then uses an executor to execute the script in the transaction. You can find more documentation about executors in the_ [_Aragon Developer Portal_](https://hack.aragon.org/docs/aragonos-ref.html#52-evmscripts)_._

`*` _These actions are very sensitive actions that will give the entity with permission to perform these actions almost complete control of your organization._

### **Kernel**

* Manage apps: install apps, upgrade apps, and change default apps in an organization. The ACL and the EVM Script Registry are default apps in the organization. Whoever has permission to perform this action can also change the default Vault contract of the organization (which is the Vault that tokens will be sent to if tokens are sent to the address of an app that is not meant to accept token deposits). `*`

`*` _These actions are very sensitive actions that will give the entity with permission to perform these actions almost complete control of your organization._

### **Tokens**

* Mint tokens: create new tokens and transfer them to a specified address
* Issue tokens: create new tokens and transfer them to the organization's Tokens app, for later assignment to a specified entity
* Assign tokens: transfer tokens held by the Tokens app to a specified entity
* Revoke vesting: revoke token vesting from a specified entity
* Burn tokens: delete tokens held by a tokenholder, reducing the total token supply

### **Voting**

* Create new votes: create a new vote
* Modify support: modify the Support parameter
* Modify quorum: modify the Minimum Approval % parameter

_Note: **“Minimum Approval %”** is the percentage of the total token supply that support for a proposal must be greater than for the proposal to be considered valid. For example, if the Minimum Approval % is set to 20%, then more than 20% of the outstanding token supply must vote to approve a proposal for the vote to be considered valid. If a vote does not make quorum, then it will fail, even if more tokens voted to approve the proposal than voted against it. For example, if the Minimum Approval % is set to 20% and 10% of the outstanding token supply votes against the proposal but only 15% vote in support, then the proposal will fail because it has not reached the Minimum Approval % threshold._

_Note: **“Support”** is the percentage of votes on a proposal that the total support must be greater than for the proposal to be approved. For example, if “Support” is set to 51%, then more than 51% of the votes on a proposal must vote “Yes” for the proposal to pass._

### **Finance**

* Create new payments: create a transfer from the Finance app to another entity
* Execute payments: trigger a recurring payment owed to an entity
* Change period duration: modify the duration in seconds between accounting periods
* Change budgets: modify how many tokens can be spent within a given accounting period
* Manage payments: enable and disable recurring payments

### **Vault**

* Transfer Vault’s tokens: transfer tokens held by the Vault app



{% embed url="https://youtu.be/kMF7Y_KPm-4?t=666" %}

