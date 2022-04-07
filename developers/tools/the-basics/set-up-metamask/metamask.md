# Sign a transaction with Metamask

## Select your account on metamask

Login to your metamask wallet,  select the account that you have imported (how to do this go [here](import-your-seed-wallet-in-metamask.md)) and select the network you are working on (for example if you are testing on a private network, select Localhost 8545).&#x20;

You've now connected MetaMask to an account that has interact in your DAO. In our example, it has the permission to increment and decrement the Counter app in our first DAO.

## Increment the Counter

Navigate to your DAO and click on the _Increment_ button in the Counter app.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-7.png)

You should see a panel slide in from the right with an error message. The message (in a blue box) basically says you can't perform any actions unless you enable MetaMask.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-8.png)

You should see that the final line inside the blue box reads: **Please unlock and enable Metamask**. Click on _enable_ and open up MetaMask again.

You should see a connection request from Aragon. Click on the _Connect_ button to accept it.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-9.png)

Now go back to the Counter app.&#x20;

## A possible error&#x20;

{% hint style="warning" %}
If you haven't connected your metamask account to the right network you got an error message 😔.
{% endhint %}

{% hint style="success" %}
If you have connected your metamask account to the right network you can skip this section and go [here](metamask.md#create-the-transaction).
{% endhint %}

In our example, the message says we need to connect MetaMask to the private network.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-10.png)

{% hint style="info" %}
Why are we getting this error?
{% endhint %}

Remember, Metamask defaults to selecting the main Ethereum network when you make a transaction. But our DAO is actually running on a private local network, not the mainnet.

{% hint style="info" %}
Why are we using a private network?
{% endhint %}

Remember that using the mainnet requires purchasing ETH with real money. And that using the mainnet or testnets requires us to download the entire past transaction history of the blockchain: this takes a considerable amount of time, and requires a lot of local disk space. In contrast, a private network requires almost no local disk space and can be operated without having to purchase ETH with real money. So it's perfect for rapid experimentation and testing.

Remember, we can connect to a local (private) network by opening up Metamask and selecting **Localhost 8545**. So let's go ahead and do that.

Close the panel and open MetaMask again. Now, click on the selected network  -  _Main Ethereum_ Network -  and select _Localhost 8545_ from the dropdown menu that appears.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-11.png)

You should now see that your account has some ETH. Quite a lot in fact. Unfortunately, this is not real ETH, but it will allow you to perform transactions within your local private network (in other words, increment and decrement the counter).

Now, go back to the _Counter app_, and click on the _Increment_ button again.

## Confirm the transaction <a href="#confirmthetransaction" id="confirmthetransaction"></a>

This time, instead of an error message, you should see an explanation of the action you are about to perform.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-12.png)

Double check that the action that's about to be triggered is the one you wish to perform. Then click on _Create transaction._

The app will now signal to you that it's waiting for your signature.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-13.png)

Open MetaMask again to sign your transaction. You'll be asked to confirm a transaction from Account 1 (your account) to the address of your newly created DAO. The total amount you're sending is about 0.001 ETH: basically just the _Gas fee_.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-14.png)

In case you're unfamiliar with the concept of **Gas**, the **Gas fee** is what's used to incentivize miners to add your transaction to the blockchain. You can think of it as a small tip. Remember that this transaction is taking place on a local (private) network, so this isn't real money. If you're happy with the details of the transaction, click on _Confirm_.

Now, if you go back to you're first DAO you should see that the counter has finally been incremented!

![](https://hack.aragon.org/docs/assets/metamask-guide/m-15.png)

{% hint style="success" %}
If you've made it all the way here, well done! You've just signed your first blockchain transaction with Metamask. 🎉🎉😊
{% endhint %}
