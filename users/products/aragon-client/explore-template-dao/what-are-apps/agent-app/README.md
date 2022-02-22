---
cover: ../../../../../../.gitbook/assets/03.png
coverY: 0
---

# Agent App

The _Agent app_ enables Aragon organizations to **interact** directly with any **other smart contract** on Ethereum.&#x20;

Before Agent, an organization would have to nominate a trusted party to interact with an Ethereum smart contract on its behalf. For example, an organization would send some $DAI to one of its employees, who would then be trusted to lend the $DAI on Compound, earn interest, and then send the interest plus the principle back to the organization.&#x20;

Now with Agent, an organization can (for example) lend its $DAI out on Compound directly, without having to trust any intermediaries.

The easiest way to start using the Agent app is to **check the box** to optionally install it when first creating your organization:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bc80204286364bc8f9029/file-zLiYZ6kXSy.png)

Note that installing Agent via one of the templates will replace the Vault app normally included with templates that do not use the Agent app.

If you did not optionally install the Agent app when first creating your organization, you can still install it after the organization has been created.&#x20;

To do so, you will need to follow the instructions for [installing and initializing the Agent app using the aragonCLI](../../../../../../developers/tools/guides/the-agent-app.md). Note that this option is geared towards experts.

Once you have the Agent app installed, the fun can begin.

## **Agent frontend interface**

The _Agent app_ currently has a **view-only frontend interface** that you can use to see which tokens are currently held by the Agent app (including ERC-20, ERC-677, and ERC-777 tokens) as well as see a history of transactions made using the Agent app. The transaction history can be filtered by transaction type, token, or date, and can be exported as a CSV file.

![Agent App page](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5e8ce5d32c7d3a7e9aea8d19/file-r5322DPQHX.png)

The Agent smart contract address is available on the _System_ menu in the _Organization_ page.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcdad2c7d3a7e9ae1a16d/file-pJP6dzQfhR.png)
