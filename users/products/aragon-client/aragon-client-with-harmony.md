---
cover: ../../../.gitbook/assets/03.png
coverY: 0
---

# Aragon Client with Harmony

[In 2021 Harmony paired with Aragon to deliver a DAO product using the client.aragon.org interface](https://blog.aragon.org/aragon-client-deployed-on-harmony/)

**In this article, we will walk you through how to deploy DAOs on the Harmony test network.**&#x20;

### Introduction

[Harmony.one](https://www.harmony.one) is an L2 Ethereum compatible blockchain network with broad compatibility, low costs, and [high transaction rates (allegedly up to 10M/sec)](https://medium.com/@aervinaervin/harmony-10million-transactions-per-second-e8161b7b7f61). It is a 'Effective Proof of Stake' network, where users can transact with each other for fraction of the Mainnet transaction costs. Assets on Ethereum can be moved to Harmony and back again using [bridges](https://docs.harmony.one/home/general/horizon-bridge/bridging-eth-one). By reducing the cost of deploying a DAO from $500+ to a few cents Aragon hopes to inspire hundreds of businesses and non-profits to enter in to the Web3 economy

#### Getting your feet wet with the Harmony Testnet

Connect your Web3 wallet to the Harmony Testnet and deposit "test-ONE". How? [Here](../set-up-metamask/getting-started-with-mumbai-testnet.md) is a good guide.&#x20;

1. ~~First you are going to add Harmony test net to metamask - follow the instructions here~~ [~~https://hack.aragon.org/docs/guides-use-metamask~~](https://hack.aragon.org/docs/guides-use-metamask) ~~and add a test network and a real one as well when you're ready~~
2. ~~Get your Harmony One address for the faucet - go to~~ [~~https://explorer.harmony.one/~~](https://explorer.harmony.one) ~~and copy the ID from your metamask wallet~~

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61db0984d268f00e10386d30/file-k4lsn7c6rW.png)

~~It should output an address that begins with one1.... you'll need to copy that address and then go to~~

~~3.~~ [~~https://faucet.pops.one/~~](https://faucet.pops.one) ~~and insert your address - wait a couple of seconds and look forward to having 1000 Test One..... enough to make DAOs for all your frens'n'fam~~

#### Getting Started with Harmony for real!

Connect your Web3 wallet to the Harmony network and deposit at least 0.2 ONE. How? [Here](../set-up-metamask/getting-started-with-harmony.md) is a good guide.&#x20;

1. ~~**Connect your Web3 wallet to the Harmony network.**~~\
   ~~~~\
   ~~We recommend using MetaMask as your Web3 wallet.~~ [~~Here~~](https://docs.harmony.one/home/network/wallets/browser-extensions-wallets/metamask-wallet) ~~is a good guide on how to connect MetaMask to Harmony.~~
2.  ~~**Deposit at least 0.2 $ONE to your Harmony wallet.**~~\
    ~~~~\
    ~~$ONE is the currency used on Harmony to pay for transaction fees and, consequently, for deploying a DAO, in the same way that $ETH is used on Ethereum.~~

    ~~At least 0.2 $ONE is required to deploy an Aragon DAO, though the actual cost might be much less.~~

    ~~$ONE may be acquired on metamask through their 'bridge'~~  [~~https://bridge.harmony.one/busd~~](https://bridge.harmony.one/busd)~~.~~&#x20;

#### Deploying a DAO

1. **Go to the** [**Aragon Client**](https://client.aragon.org/#/) **page.**

![](../../../.gitbook/assets/file-WwpvtTSvLt.png)

1.  Click "Connect account" and select your wallet provider. In the example below, we have connected our MetaMask account to the Harmony network. If the dialogue box says that it is connected to another network, switch your wallet to the Harmony network. The connected network is automatically derived from the network selected on the wallet


2. **Click "Create an Organization" and follow** [**this tutorial**](https://help.aragon.org/article/94-creating-an-new-dao-from-template) **that will run you through the creation process.**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/61db019ca6a5ee76d8a2e9cd/file-xKHkRPU0F6.png)
