# Set up Metamask Wallet

{% hint style="info" %}
In this section, you will learn how to set up a Metamask wallet and how to configure it on the different blockchains.
{% endhint %}

Where can I download the wallet? How can I set up it for the different networks? How to send funds to my wallet?&#x20;

This section replies to all and other questions about your Web3 wallet:relaxed:.

We recommend using [MetaMask](https://metamask.io) as your Web3 wallet. Metamask is a browser plugin that lets you make Ethereum (and other blockchains) transactions through regular websites. ****&#x20;

## Getting started <a href="#getting-started" id="getting-started"></a>

Visit the [Metamask homepage](https://metamask.io) and download the relevant browser extension (this guide will be based around the Chrome extension, but the process is similar for all browsers).

Once it's downloaded, you should be automatically directed to a welcome page.

![Metamask welcome Page](https://hack.aragon.org/docs/assets/metamask-guide/m-0.png)

Follow the instructions carefully. They should be pretty self-explanatory. If you need more info you can go [here](https://docs.polygon.technology/docs/develop/metamask/hello/).

Once your MetaMask setup is complete, you should be redirected to your newly created Ethereum wallet.

![Metamask account](<../../../.gitbook/assets/mm account (1).png>)

{% hint style="success" %}
If you've made it this far, congratulations 🎉.
{% endhint %}

## Account address <a href="#account-address" id="account-address"></a>

If you click on the _Three Dots_ button below your account name  - in our case _Account 1_ -  a popup will appear with your account address. It should look something like this:

> **0x931D387731bBbC988B312206c74F77D004D6B84b**

This is your **public address** (or public key). You can share this with other people to receive ETH or other tokens.

## Selected networks <a href="#selected-networks" id="selected-networks"></a>

In the top right you should see a dropdown menu with _**Main Ethereum Network**_ selected.

With this option selected, you're able to interact directly with the main Ethereum blockchain. If you click on it however, you should see that you have the ability to select other networks.

![Drop down menu for selecting the network.](https://hack.aragon.org/docs/assets/metamask-guide/m-2.png)

Why would we need to select other networks? Simply put, before launching a project (or dapp) on the main Ethereum network, it's good practice to deploy a version to an Ethereum test network. Or, simply,  you want to use a network with save cost fees (like Polygon or Harmony).

The main reason for using a testnet is that Testnet ETH can be obtained without having to pay real money. This gives developers and the community a chance to iron out any problems before real money is involved.

There are four testnets: **Ropsten**, **Kovan**, **Rinkeby**, and **Goerli**.

Don't worry about the precise differences between them at this stage. All you need to know is that they simulate Ethereum and can be used without having to pay real money.

Finally, you can also interact with private Ethereum networks by selecting **Localhost 8545**. Private in this case doesn't mean more secure. It just means that the nodes are not connected to the main or test network nodes. Perfect for rapid experimentation and testing.

{% hint style="warning" %}
Remember that if you want to use different networks, you need to set up your wallet and load your wallet with enough funds for paying the transaction fees. We will explain how to do this in the next sections.
{% endhint %}
