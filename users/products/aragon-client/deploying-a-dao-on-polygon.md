---
cover: ../../../.gitbook/assets/03.png
coverY: 0
---

# Deploying a DAO on Polygon

**In this article, we will walk you through how to deploy DAOs on the Polygon network.**&#x20;

## <mark style="color:purple;">Introduction</mark>

[Polygon](https://polygon.technology) is an [L2 scaling solution](https://ethereum.org/en/developers/docs/scaling/layer-2-rollups/) for Ethereum. It is a 'Proof of Stake' network, where users can transact with each other for fraction of the Mainnet transaction cost. Assets on Ethereum can be moved to Polygon and back again using [bridges](https://support.opensea.io/hc/en-us/articles/1500012881642-How-do-I-transfer-ETH-from-Ethereum-to-Polygon-). Ethereum fees are proportional to the complexity of the transaction but Polygon enables complex transactions for very low cost without leaving the Ethereum ecosystem. This is why Aragon has deployed its DAO infrastructure to Polygon, effectively reducing the cost of deploying a DAO from $500+ to a few cents.

### Getting Started with Polygon

1. **Connect your Web3 wallet to the Polygon network.**\
   We recommend using MetaMask as your Web3 wallet. [Here](https://docs.matic.network/docs/develop/metamask/config-polygon-on-metamask) is a good guide on how to connect MetaMask to Polygon.
2.  **Deposit at least 0.2 $MATIC to your Polygon wallet.**\
    $MATIC is the currency used on Polygon to pay for transaction fees and, consequently, for deploying a DAO, in the same way that $ETH is used on Ethereum.

    At least 0.2 $MATIC is required to deploy an Aragon DAO, though the actual cost might be much less.

    $MATIC may be bought on a decentralized exchange such as [UniSwap](https://app.uniswap.org/#/swap), using $ETH or any other ERC20 token. That $MATIC will then need to be transferred onto the Polygon network using a 'bridge' such as [https://wallet.matic.network/bridge](https://wallet.matic.network/bridge). Alternatively, $MATIC may be bought from a centralized exchange, such as Binance or Kucoin and then sent directly to your Polygon wallet.

#### Deploying a DAO

1. **Go to the** [**Aragon Client**](https://client.aragon.org/#/) **page.**

![](<../../../.gitbook/assets/file-WwpvtTSvLt (2).png>)

1. Click "Connect account" and select your wallet provider. In the example below, we have connected our MetaMask account to the Polygon network. If the dialogue box says that it is connected to another network, switch your wallet to the Polygon network. The connected network is automatically derived from the network selected on the wallet.
2. Click "Create an Organization" and follow [this tutorial](https://help.aragon.org/article/94-creating-an-new-dao-from-template) that will run you through the creation process.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6139f3ebd3b029285070f569/file-MSqrvMAds0.png)
