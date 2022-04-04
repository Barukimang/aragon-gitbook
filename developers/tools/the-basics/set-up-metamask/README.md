# Setting up a Metamask Wallet

{% hint style="info" %}
In this section, you will learn how to set up a Metamask wallet and how to configure it on different blockchains.
{% endhint %}

{% hint style="success" %}
#### We recommend using [Metamask](https://metamask.io) as your Web3 wallet.&#x20;

Metamask is a browser plugin that lets you make Ethereum (and other blockchains) transactions through regular websites. ****&#x20;
{% endhint %}

{% hint style="warning" %}
This guide focuses on a Chrome extension. However, the process is similar for all browsers.
{% endhint %}

## Keynote <a href="#getting-started" id="getting-started"></a>

For creating and using an Aragon **Client DAO** directly using command-line you need to connect to one test or one main network. You can choose from different blockchains:

* [Ethereum Mainnet](../../../../users/products/set-up-metamask/getting-started-with-ethereum.md)
* [Rinkeby Testnet](../../../../users/products/set-up-metamask/getting-started-with-rinkeby-testnet.md)
* [Polygon](../../../../users/products/set-up-metamask/getting-started-with-polygon.md)
* [Mumbai Testnet](../../../../users/products/set-up-metamask/getting-started-with-mumbai-testnet.md)
* [Harmony](../../../../users/products/set-up-metamask/getting-started-with-harmony.md)
* [Harmony Testnet](../../../../users/products/set-up-metamask/getting-started-with-harmony-testnet.md)
* [Stardust testnet](../../../../users/products/set-up-metamask/getting-started-with-metis-andromeda.md)
* [BSC Testnet](../../../../users/products/set-up-metamask/getting-started-with-bsc-testnet.md)

Let's start to configure and understand the main futures of the metamask wallet and then you can pass to choose your favorite network.

## Getting started <a href="#getting-started" id="getting-started"></a>

* Visit the [Metamask homepage](https://metamask.io) and download the browser extension. Once it is downloaded, you should be automatically directed to a welcome page.&#x20;

![Metamask welcome PageFollow the instructions carefully. ](https://hack.aragon.org/docs/assets/metamask-guide/m-0.png)

* Set up your Metamask account accordingly.

{% hint style="info" %}
If you need more info regarding creating your own Metamask profile, you can go [here](https://docs.polygon.technology/docs/develop/metamask/hello/).
{% endhint %}

* Once your Metamask setup is complete, you should be redirected to your newly created Ethereum wallet.

![Metamask account](<../../../../.gitbook/assets/mm account (1).png>)

{% hint style="success" %}
If you have made it this far, congratulations 🎉.
{% endhint %}

## Account address <a href="#account-address" id="account-address"></a>

If you click on the **"three dots"** button below your account name - in our case _Account 1_ - a popup will appear with your account address. It should look similar to the example below:

> **0x931D387731bBbC988B312206c74F77D004D6B84b**

{% hint style="success" %}
This is your public address (or public key). You can share this with other people to receive ETH or other tokens.
{% endhint %}

## Selected networks <a href="#selected-networks" id="selected-networks"></a>

In the top right you should see a dropdown menu with _**Main Ethereum Network**_ selected. With this option, you are able to interact directly with the main Ethereum blockchain.&#x20;

#### If you click on it, a selection of other networks will be shown.

![Drop down menu for selecting the network.](https://hack.aragon.org/docs/assets/metamask-guide/m-2.png)

## Why should you select other networks?&#x20;

Before launching a project (or Dapp) on the main Ethereum network, it is good practice to deploy a version to an Ethereum test network or on other main networks (like Polygon or Harmony) to save on costs for transaction fees.

### The benefits of using a testnet

The main reason for using a testnet ETH is that it can be obtained without having to pay real money. This gives developers and the community a chance to iron out any problems before real money is involved.

#### There are four testnets:&#x20;

* Ropsten
* Kovan
* Rinkeby
* Goerli

{% hint style="warning" %}
**At this stage don't worry about the differences between these networks.** All you need to know is that they simulate Ethereum and can be used without having to pay real money.
{% endhint %}

### Using private networks

Finally, you can also interact with private Ethereum networks by selecting **Localhost 8545**. Private in this case doesn't mean more secure. It just means that the nodes are not connected to the main or test network nodes. **Perfect for rapid experimentation and testing.**

{% hint style="warning" %}
Remember that if you want to use different networks, you need to set up your wallet and load your wallet with enough funds for paying the transaction fees. We will explain how to do this in the next sections.
{% endhint %}
