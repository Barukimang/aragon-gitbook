---
description: How the user experiences an Aragon DAO
---

# The Aragon client

The [Aragon client](https://github.com/aragon/aragon) is a full dapp that can create and manage decentralized organizations by running Aragon apps inside it.

The client provides Aragon app developers with the following capabilities:

* **Sandboxing**: The client is running code from third party developers and so in order to mitigate risk (such as cross-site scripting and phishing attempts by manipulating the DOM) we sandbox apps
* **App listing**: It traverses the organization to find all the relevant apps for it
* **Transaction pathing**: It checks with the [ACL](https://hack.aragon.org/docs/acl-intro) to see if the user can perform an action (e.g. withdrawing funds) and if not, it gives the user alternative paths to perform it (e.g. maybe by opening a vote)
* **Human readable transactions**: It uses [Radspec](https://hack.aragon.org/docs/human-readable-txs) and describes the user action in a human readable way
* **Notifications**: Aragon apps can send notifications to the user when something relevant happens

It looks like this: ![](https://raw.githubusercontent.com/aragon/aragon-wiki/master/docs/media/press/press-kit/screenshots/0.5/aragon\_core\_v05\_beta\_home04.png)

\
