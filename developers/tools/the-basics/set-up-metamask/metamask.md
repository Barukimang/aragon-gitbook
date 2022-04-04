# Sign a transaction with Metamask

## Using your created account on metamask.

Now, what you need to do is to look at the output of your terminal after you ran `npm start`. You should see the following at the end:

```
ℹ The accounts were generated from the following mnemonic phrase:
explain tackle mirror kit van hammer degree position ginger unfair soup bogus
```

These 12 words phrase will allow us to use MetaMask to access an account that has permission to update the Counter in our Counter app. Import this seed to metamask as described [here.](https://app.gitbook.com/o/3h8kxj8geKVXgyMnGbYT/s/zhQIP88M8McmSaEGSymT/\~/changes/abgRqrELBOMTheWAlezk/users/products/set-up-metamask/import-your-seed-wallet-in-metamask)

You've now connected MetaMask to an Ethereum account that has permission to increment and decrement the Counter app in your first DAO.

We're now finally ready to play with the Counter app 😊.

Navigate back to your DAO and click on the **Increment** button in the Counter app.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-7.png)

You should see a panel slide in from the right with an error message. The message (in a blue box) basically says you can't perform any actions unless you enable MetaMask.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-8.png)

You should see that the final line inside the blue box reads: **Please unlock and enable Metamask**. Click on **enable** and open up MetaMask again.

You should see a connection request from Aragon. Click on the **Connect** button to accept it.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-9.png)

Now go back to the Counter app. Oh dear… we have another error message 😔. This time, the message says we need to connect MetaMask to the private network.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-10.png)

Why are we getting this error?

Remember, Metamask defaults to selecting the main Ethereum network when you make a transaction. But our DAO is actually running on a private local network, not the mainnet.

Why are we using a private network?

Remember that using the mainnet requires purchasing ETH with real money. And that using the mainnet or testnets requires us to download the entire past transaction history of the blockchain: this takes a considerable amount of time, and requires a lot of local disk space. In contrast, a private network requires almost no local disk space and can be operated without having to purchase ETH with real money. So it's perfect for rapid experimentation and testing.

Remember, we can connect to a local (private) network by opening up Metamask and selecting **Localhost 8545**. So let's go ahead and do that.

Close the panel and open MetaMask again. Now, click on the selected network  - **Main Ethereum Network** -  and select **Localhost 8545** from the dropdown menu that appears.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-11.png)

You should now see that your account has some ETH. Quite a lot in fact. Unfortunately this is not real ETH, but it will allow you to perform transactions within your local private network (in other words, increment and decrement the counter).

Now, go back to the **Counter app**, and click on the **Increment** button again.

This time, instead of an error message, you should see an explanation of the action you are about to perform.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-12.png)

Double check that the action that's about to be triggered is the one you wish to perform. Then click on **Create transaction**.

The app will now signal to you that it's waiting for your signature.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-13.png)

Open MetaMask again to sign your transaction. You'll be asked to confirm a transaction from Account 1 (your account) to the address of your newly created DAO. The total amount you're sending is about 0.001 ETH: basically just the **Gas fee**.

![](https://hack.aragon.org/docs/assets/metamask-guide/m-14.png)

In case you're unfamiliar with the concept of **Gas**, the **Gas fee** is what's used to incentivize miners to add your transaction to the blockchain. You can think of it as a small tip. Remember that this transaction is taking place on a local (private) network, so this isn't real money. If you're happy with the details of the transaction, click on **Confirm**.

Now, if you go back to you're first DAO you should see that the counter has finally been incremented!

![](https://hack.aragon.org/docs/assets/metamask-guide/m-15.png)

If you've made it all the way here, well done! You've just signed your first blockchain transaction with Metamask. 🎉🎉😊
