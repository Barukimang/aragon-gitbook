---
cover: ../../../../../.gitbook/assets/03.png
coverY: 0
---

# Finance App

The _Finance app_ is used to manage the financial resources of an organization. You can:

* see **the balance** of each asset the organization owns,&#x20;
* see a **history** of past transfers
* create **new transfers** from the Finance app

![](<../../../../../.gitbook/assets/Schermata 2022-02-09 alle 09.52.02.png>)

### <mark style="color:blue;">**Token Balance**</mark>

The _Token Balances_ section shows you the balance of each token owned by the organization.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62772c7d3a7e9ae190b0/file-eLUV9SRU2y.png)

### <mark style="color:blue;">**Transfers**</mark>

The _Transfers_ section shows you a history of past transfers that have been made using the Finance app, including information about the date of the transfer, what address the transfer was to or from, a reference with additional context about the transfer, and the amount of the transfer.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62832c7d3a7e9ae190b1/file-5lFKotQ4xB.png)

The transfer history can be filtered by date:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a629604286364bc8f80c5/file-TXwf7noy6I.png)

Or token symbol:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62a52c7d3a7e9ae190b8/file-HWRr2HXIlA.png)

Or transfer type:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62b62c7d3a7e9ae190b9/file-vWgrnBRGM4.png)

For each transfer, you can click on the drop down menu to get a link to view the transaction on the blockchain so you can see even more detail about the transfer:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62c904286364bc8f80cc/file-Puf5b59tKe.png)

And if you need to export your transfer history for accounting in a separate app, there's an export button that you can use to export a CSV file:

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a62e604286364bc8f80ce/file-wgYMOA7KJK.png)

Follow these steps to create a new transfer from the Finance app:

### <mark style="color:blue;">**New Transfer**</mark>

**Deposit Funds:** to send funds to your organization, you can create a deposit using the Finance app:

* click the _New Transfer_ button,&#x20;
* open the _Deposit_ tab,&#x20;
* select the token you want to deposit,&#x20;
* enter the amount&#x20;
* enter an (optional) reference note,&#x20;
* then click the _Submit deposit_ button.

_Note: For non-ETH tokens, two transactions may be required to make a deposit. The first transaction approves the Finance app to pull the deposit amount from your account balance, and the second transaction is the actual deposit transaction. This is a safety feature to prevent the Finance app from pulling more funds from your account than you have explicitly authorized._

**On testnet**: go to the Organizations app and press the _**Request test tokens**_ button. Open your Ethereum provider to sign and send the transaction. About a minute or so after your transaction is confirmed, test tokens will be available in the Finance app of your organization. You can then create a new transfer to send these tokens to another address.\


![Deposit Funds - Finance App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a631b2c7d3a7e9ae190c3/file-PVF6PN5gbK.png)

**Withdrawal funds:** to create a new transfer from your organization to another address, you can create a withdrawal using the Finance app:

* click the _New Transfer_ button,&#x20;
* open the _Withdrawal_ tab,&#x20;
* enter the address you want to make the transfer to,&#x20;
* enter what token you want to send,&#x20;
* enter the amount of tokens you want to send.&#x20;
* add (optionally) a reference note to provide more context for the transfer.&#x20;

Once you have filled out all of this information you can click the _Submit transfer_ button to complete the action, if you have permission.

![Withdrawal funds - Finance App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a63252c7d3a7e9ae190c4/file-L9njobkDLU.png)



### <mark style="color:blue;">**Sign the transaction to create the New Transfer vote**</mark>

As mentioned before, all actions in the Company organization require a vote by tokenholders. Click “Create transaction” then open your Ethereum provider to sign and send the transaction that creates the New Transfer vote.

![](https://lh3.googleusercontent.com/UXQwChFz66jOLkHe2GvPoJ\_dTc0dWafDE1aUsgS6GVP47AlL\_RNwSvBTLzZqQDq4M8rxpts6acwsYr2MIO4dRBwjJ6S56h8G1-w9f5c\_FJAK8usZabmT5WbQvR5bqCCXPr-fiGiX)

### <mark style="color:blue;">**Vote on the transfer**</mark>

The transfer has to be approved by tokenholders. Cast a "Yes" vote to approve the transfer and have the other tokenholders in the organization vote as well.

![](https://lh3.googleusercontent.com/BYjI\_u7oOJgw6s6\_0IVRxQy\_AAkEHiuc8aQes9a71HZNEknuNwO8FttrpeszbMIXY2j6AV7FfytR-eUi4Y\_eoILA\_WGjHiCz1cYasmUfj\_A0uhmod3bkh1ezWT6IhfP0GmyFmVG7)

### <mark style="color:blue;">**The vote transaction is signed and sent to approve the transfer**</mark>

After confirmation, the transfer will execute.

![](https://lh4.googleusercontent.com/C86GPoGAqAHhOiN-534hCWcWFeLBfwv3gsnEZ\_aXKwbYeaj67c8nNnvb3\_AK5fEAwPm03a-btdc-mLNkdy\_u-ezuZQG-g7iAvtjfHFoBmZxpYLoukXi7FT88VWifr79\_L21sGjxC)