# Using the Company Template

{% hint style="info" %}
In this section, you will learn how to create a Company DAO using the Company Template in the Aragon Client.&#x20;
{% endhint %}

{% hint style="danger" %}
Before starting:  be sure to have read the "[How to create a DAO](./)" section.
{% endhint %}

A _Company_ organization is an organization that uses **transferable tokens** to represent stake in the company. Decisions are made using **token-weighted voting**, where one token equals one vote.

## Creating a Company DAO

![Select the template](<../../../../.gitbook/assets/Schermata 2022-02-04 alle 18.41.40.png>)

Click _View details_, review the apps available, check the boxes to install any optional apps you want to install. When finished, click _Use this template_.

![Company template](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## Claim a name

Select the name of your DAO and fill in the _Organization Name_ tab.&#x20;

Aragon uses the [Ethereum Name Service](https://ens.domains) (ENS) to assign names to organizations.

Note: this name will be useful for accessing your DAO. Don't forget it!&#x20;

![Select a DAO name](<../../../../.gitbook/assets/Schermata 2022-02-04 alle 18.52.45.png>)

## Configure the parameters of the Voting App

_Note: The Voting app parameters currently cannot be changed from the Aragon front-end client. To change the Voting app parameters after your organization has been created, you must first initialize the permissions to change these parameters, then you can change the parameters using the_ [_aragonCLI_](https://hack.aragon.org/docs/cli-intro.html)_._

Configure the voting settings. Select:

* the S_upport_ percentage: is the relative percentage of tokens that are required to vote “Yes” for a proposal to be approved. For example, if “Support” is set to 50%, then more than 50% of the tokens used to vote on a proposal must vote “Yes” for it to pass.
* the _Minimum Approval_ percentage: is the percentage of the total token supply that is required to vote “Yes” on a proposal before it can be approved. For example, if the “Minimum Approval” is set to 20%, then more than 20% of the outstanding token supply must vote “Yes” on a proposal for it to pass.
* the _Vote Duratio_n: is the length of time that the vote will be open for participation. For example, if the Vote Duration is set to 24 hours, then token holders have 24 hours to participate in the vote.

![Configure the Voting settings](<../../../../.gitbook/assets/Schermata 2022-02-04 alle 19.01.42.png>)

## Configure the parameters of the Token App

Choose a token name, a symbol, the tokenholders and the amount (_balance_) of token for each tokenholders. You can add the token holder using the _Add more_ button.

Note: The token name and symbol currently cannot be changed. Do not add more than a few tokenholders to your organization on this screen or the transaction to create your organization may fail; you can add more tokenholders after the organization has been created.

![Token app settings](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## Review organization information

Open each panel to make sure that the information entered to launch your organization is correct. If anything is incorrect, you can click the "back" button to return to an earlier screen and make the necessary correction.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)



![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![
](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## Launch your organization

Now you need to sign a transaction to create your organization. Open your Ethereum provider if the window does not open automatically. Click the _confirm_ button in your Ethereum provider to sign and broadcast the transaction.

Wait until the transaction is completed.&#x20;

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

Don't close or refresh the page until the process is completed and the DAO is deployed.&#x20;

## Click "Get started"&#x20;

{% hint style="success" %}
Your new Company organization is ready to go!
{% endhint %}

Now you can [explore your new Company organization](../explore-template-dao/).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)

If your DAO doesn't open automatically, go [here](../../../../faq/products/aragon-client/where-is-my-dao.md) and find how to access it.



> #### <mark style="color:purple;">Do you have a question? Leave your comments here at our Discourse forum</mark> 👇

{% embed url="https://aragontesting.trydiscourse.com/t/aragon-client-company-template/32" %}
