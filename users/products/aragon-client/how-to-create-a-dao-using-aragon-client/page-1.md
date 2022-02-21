# Use the Reputation template

{% hint style="info" %}
&#x20;In this section, you will learn how to create a Reputation DAO using the Reputation Template in the Aragon Client.&#x20;
{% endhint %}

{% hint style="danger" %}
Before starting:  be sure to have read the "[How to create a DAO](./)" section.
{% endhint %}

A _Reputation_ organization is an organization that uses **non-transferable tokens** to represent reputation. Decisions are made using **reputation-weighted voting**.

Creating a Reputation DAO:

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.02.19.png>)



Click _View details_, review the apps available, check the boxes to install any optional apps you want to install. When finished, click _Use this template_.

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.22.29.png>)

### <mark style="color:blue;">Claim a name</mark>

Select the name of your DAO and fill in the _Organization Name_ tab.&#x20;

Aragon uses the [Ethereum Name Service](https://ens.domains) (ENS) to assign names to organizations.

Note: this name will be useful for accessing your DAO. Don't forget it!&#x20;

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.23.36.png>)

### <mark style="color:blue;">Configure the parameters of the Voting App</mark>

_Note: The Voting app parameters currently cannot be changed from the Aragon frontend client. To change the Voting app parameters after your organization has been created, you must first initialize the permissions to change these parameters, then you can change the parameters using the_ [_aragonCLI_](https://hack.aragon.org/docs/cli-intro.html)_._

Configure the voting settings. Select:

* the S_upport_ percentage: is the relative percentage of tokens that are required to vote “Yes” for a proposal to be approved. For example, if “Support” is set to 50%, then more than 50% of the tokens used to vote on a proposal must vote “Yes” for it to pass.
* the M_inimum Approval_ percentage: is the percentage of the total token supply that is required to vote “Yes” on a proposal before it can be approved. For example, if the “Minimum Approval” is set to 20%, then more than 20% of the outstanding token supply must vote “Yes” on a proposal for it to pass.
* the V_ote Duratio_n: is the length of time that the vote will be open for participation. For example, if the Vote Duration is set to 24 hours, then token holders have 24 hours to participate in the vote.

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.08.36.png>)



### <mark style="color:blue;">Configure the parameters of the Token App</mark>

Choose a token name, a symbol, the tokenholders and the amount (_balance_) of token for each tokenholders. You can add the token holder using the _Add more_ button.

Note: The token name and symbol currently cannot be changed. Do not add more than a few tokenholders to your organization on this screen or the transaction to create your organization may fail; you can add more tokenholders after the organization has been created.

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.03.png>)

### <mark style="color:blue;">Review organization information</mark>

Open each panel to make sure that the information entered to launch your organization is correct. If anything is incorrect, you can click the "back" button to return to an earlier screen and make the necessary correction.

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.25.54.png>)

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.03.png>)

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.26.14.png>)

### <mark style="color:blue;">Launch your organization</mark>

Now you need to sign a transaction to create your organization. Open your Ethereum provider if the window does not open automatically. Click the _confirm_ button in your Ethereum provider to sign and broadcast the transaction.

Wait until the transaction is completed.&#x20;



![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Don't close or refresh the page until the process is completed and the DAO is deployed.&#x20;

### <mark style="color:blue;">Click "Get started"</mark>&#x20;

Your new Reputation organization is ready to go!

Now you can [explore your new Reputation organization.](../explore-template-dao/)

![](<../../../../.gitbook/assets/Schermata 2022-02-10 alle 15.17.04.png>)

If your DAO doesn't open automatically, go [here](../../../../faq/products/aragon-client/where-is-my-dao.md) and find how to access.
