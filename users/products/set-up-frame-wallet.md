# Set up Frame Wallet

{% hint style="info" %}
Important info: In this section, you will learn how to get started with Frame and interact with a DAO using a hardware wallet.
{% endhint %}

## **Install Frame**

Go to the [Frame website](https://frame.sh) and install the Frame desktop client and browser extension.

![Download Frame Page](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8bcfb504286364bc8f9089/file-RW9LeLOUHS.png)

## Setup

> You need a Metamask, Ledger, or Trezor wallet to use Frame.&#x20;

Start by downloading Frame from the official website: [https://frame.sh](https://frame.sh). After installation Frame stays quietly in your menu bar until it's needed.

![](https://hack.aragon.org/docs/assets/frame/frame-intro.gif)

## Configure your device <a href="#configure-your-device" id="configure-your-device"></a>

### **Metamask**

To import your Metamask wallet into Frame:

* Click on the _+_ button in the Accounts bar in top of the wallet
* Click on the _add new accounts_ button in the frame which pop-ups on the right
* Click on the _seed phrase_ button
* Copy and paste the seed phrase from your Metamask wallet and click _next (see image below)_
* Your Metamask wallet should now appear in the Frame wallet

![](<../../.gitbook/assets/Screenshot 2022-02-23 at 17.04.36.png>)

### **Ledger**

On Ledger devices insert your pin on the device to unlock it and then open Frame.

![](https://hack.aragon.org/docs/assets/frame/frame-ledger.gif)

### **Trezor**

On Trezor devices insert your pin directly on Frame.



![](https://hack.aragon.org/docs/assets/frame/frame-trezor.gif)

You should now be able to select the network and account you would like to use.

### **Network**

To choose the appropriate network, select the button on the upper right corner (the three arrows). This will take you to Frame's menu, where you can configure its general settings. We will focus on the _Connection_ option. Right now the default is Rinkeby but you can also choose Mainnet, Ropsten or Kovan.

For this tutorial we will select Rinkeby.



![](https://hack.aragon.org/docs/assets/frame/frame-app-menu.gif)

### **Accounts**

The last step is to choose your account. Click on the configuration button (the button to the right of the Ledger or Trezor icon) and then click on the accounts button that pops up below the icon. This will display a new menu with the available accounts on your device for the network. Select one with some test-ether (if you don't have any, you can request a Rinkeby faucet [here](https://faucet.rinkeby.io) or [here](https://faucets.chain.link/rinkeby)).



![](https://hack.aragon.org/docs/assets/frame/frame-accounts.gif)

In the configuration menu you can also manage the Dapp permissions you have granted for that particular account. We'll explain more about this in [this section](../../developers/tools/guides/signers/frame.md).

{% hint style="success" %}
You are now finished setting up Frame for your device, and are ready to sign your first transaction!
{% endhint %}
