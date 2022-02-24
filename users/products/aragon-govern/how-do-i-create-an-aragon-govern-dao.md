---
cover: ../../../.gitbook/assets/60a39be473bc185893775da8_govern.png
coverY: 0
---

# How do I create an Aragon Govern DAO?

Creating a Govern DAO is a quick and easy process.

Go to [https://govern.aragon.org/#/create-dao](https://govern.aragon.org/#/create-dao) and fill out all the relevant information regarding your DAO.

## <mark style="color:purple;">Basic Information</mark>

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61155889b55c2b04bf6ddda0/file-jQxSjLKpa8.png)

In this first step you should define:

\- **DAO identifier**: This will be your DAO unique identifier, and will be used as part of the URL to directly access your DAO. It cannot contain spaces, and should not have already being used by another DAO. Try and name it something unique that relates to your community only (eg. "space\_invaders\_gamers\_dao").&#x20;

\- **DAO token**: Fill out the information about the token your community will use to govern your DAO.&#x20;

\- If you don't have a token yet, choose the **New Token** option, and fill out the token name, token symbol, and how many tokens you would like to mint initially. You can mint more tokens in the future, or even change the token contract to restrict future further minting. All the minted tokens will initially be sent to your wallet.

\- If you already have a token, choose the **Existing Token** option and add your token address to it.&#x20;

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61155a2d21ef206e5592aff7/file-6re43pNq8c.png)

Currently, there is no practical usage for the token information within the DAO. But future usages are foreseen.

\- **Proxies**: When selecting this option you will drastically reduce the amount of gas needed to deploy your DAO. This means that instead of deploying a whole smart contract to be the executor of your DAO (The one that executes transactions as the DAO), you will just deploy a proxy contract (which is a minimal version that forwards requests to a full contract that was already deployed by Aragon).&#x20;

<mark style="color:blue;background-color:red;">Important:</mark> This option **DOES NOT** reduce the security of your DAO in any way.

## <mark style="color:purple;">Configuration</mark>

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6115589a6ffe270af2a9855f/file-jLdUKuX5Ov.png)

In this step you should define:

\- **Execution delay**: The amount of time a given transaction will be on hold before being executed. During this period, the transaction can be reviewed by your community members, and if it does not conform with your DAO agreement, it can be challenged. At the end of the delay period, the transaction will be available for execution. [Learn more](https://help.aragon.org/article/103-why-transactions-have-a-delay-time-to-be-executed).

\- **Rules & Agreement**: An Aragon Govern DAO works thanks to optimistic governance: it expects its members to act in its best interest, and for these to always follow a specific set of (pre-agreed) rules. These rules are what make a DAO agreement, and can be provided as free text, pdf, or document.&#x20;

\- **Dispute resolution client**:  This is the address of a smart contract that can act as a dispute resolution system for the optimistic governance model to be enacted. The default address is set to Aragon Court, a tested and secure dispute resolution system by Aragon. Be aware that if you change this address, and the new smart contract does not implement the [ERC3k standard](https://eips.ethereum.org/EIPS/eip-3000), or it relies on an insecure system, you might make your DAO unusable or allow funds to be stolen.

## <mark style="color:purple;">Collateral</mark>

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611558bd64a230081ba1eaec/file-dYJrDvkzgq.png)

In this step you should:

\- **Schedule execution collateral token**: This is the token that will be required by any member to detain before they can schedule a transaction. Members who do not own the amount of tokens you define here, will not be able to schedule any transaction. [Learn more about collaterals](https://help.aragon.org/article/104-understanding-collaterals-in-aragon-govern).

\- **Challenge execution collateral token**: This is the token that will be required by any member to detain before they can challenge a transaction. Members who do not own the amount of tokens you define here, will not be able to challenge any transaction. [Learn more about collaterals](https://help.aragon.org/article/104-understanding-collaterals-in-aragon-govern).

\- **Whitelist of addresses (optional):** This is an additional safeguard step you might want to add to your DAO. If you select any address, any member that owns the schedule execution collateral can schedule transactions. This said, if you want to grant only a subset of members permission, you can set the list here.&#x20;

Important: If a wallet address is in the whitelist, it still needs to hold the collateral token to schedule a transaction.

Lastly, it is time to review the information to make sure everything is correct. If you are happy with itit, just go ahead and click the "Confirm and Create a DAO" button.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611559fdb55c2b04bf6dddb3/file-fxIiexUROg.png)
