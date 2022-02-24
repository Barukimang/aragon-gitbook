---
cover: ../../../.gitbook/assets/03.png
coverY: 0
---

# MultiSig

In this article, we will look into how Aragon Client DAOs can be managed by a MultiSig wallet.

Here we are going to use Gnosis Safe MultiSig, however, you could follow a similar approach for any other MultiSig wallet that supports contract interaction.

### Prerequisites:

#### Assign the desired permissions in the Client DAO to the MultiSig

Aragon Client DAOs have an access control system, where each action is protected by a set of permission records. Only someone who has specific permission can perform the action. You can read more about permissions [here](https://hack.aragon.org/docs/acl-intro).

That is why we need to assign the MultiSig wallet to a range of permissions that correspond to the actions we want it to be able to perform.

Follow the steps below to assign permission to a MultiSig or have a look at this [article](https://help.aragon.org/article/21-permissions):

1\. Open your DAO portal and select the permissions tab on the left. Here you can examine the permissions you have within your DAO.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/6112718fb55c2b04bf6dce7e/file-DCOHNWElgt.png)

2\. To add a new one permission press the "New permission" button.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611272116ffe270af2a97627/file-D7HYuaQgTh.png)

3\. Select the App you want to create permission for.

4\. Select which entity will be assigned the new permission. To add the MultiSig address select "Custom Address" and enter the address in the field below.

5\. Select an action we want to grant permission to. In our case, we are assigning permission for a MultiSig to create new votes within our DAO.

6\. Press "Add permission". This might create a vote depending on your DAO structure and who is this action's permission manager.

7\. Revoke the undesirable permissions. To do so expand any permission and press onto the dustbin icon.

**NB!** Please be cautious, as incorrect permissions could make your DAO vulnerable or inaccessible.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611275a7b37d837a3d0e2535/file-AecSpNvGSO.png)

**Result:**

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0ef364a230081ba1ce2f/file-aDCnpa7wjo.png)\_\_

_Here we have assigned MutliSig permissions to manage payments and change voting support parameters within the DAO. However because we have kept voting as the Permission Manager, community members will be able to vote to remove these permissions effectively revoking this MultiSigs control over the DAO._

### Executing actions:

1\. Go to [Gnosis Safe](https://gnosis-safe.io) website and connect to their DApp

2\. Open your vault

3\. Press "New Transaction" button and select "Contract Interaction"

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d0efb766e8844fc34e2c5/file-ery56Brop6.png)

4\. Into the Contract address input the address of the Aragon App you would like to interact with.

You can find it on the "Organisations" page of your DAO portal. Look at the "INSTALLED ARAGON APPS" section there.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d1014766e8844fc34e2cd/file-8cuqErvYC1.png)

5\. This will automatically populate the ABI field. Delete the content that appeared there.

6\. Find the base contract of the selected Aragon App that you would like to interact with

a. Open the address that you have used in step 4 on [etherscan](https://etherscan.io).

b. Go to "Contract"

c. Select "Read contract"

d. Expand "implementation"

e. Open the address that appeared under "implementation" on [etherscan](https://etherscan.io).

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d115d766e8844fc34e2ce/file-g3POvBnP7e.png)

7\. Copy the ABI of the opened address to the field in step 5

a. Go to "Contract"

b. Select "Code"

c. Locate "Contract ABI"

d. Copy the ABI to the Gnosis Safe ABI input field

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/610d12f1766e8844fc34e2d7/file-nCgkCpoDAD.png)

8\. Select the method you want to use and populate the parameters. Here we will create a new immediate payment from the Finance app. It will transfer 0.1 ETH (represented by a 0x0..0 token address) to the 0x424... address.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611277e1766e8844fc34f0ab/file-xlkaRMNQ6n.png)

9\. Press "Review" and "Submit". After enough people sign the transaction you will be able to view it on Etherscan and once it has been confirmed it should take effect on the DAO.

### Possible Issues:

1. Make sure you have the permissions to invoke this method from the Gnosis Safe address
2. If gas estimation has failed and you get warnings there has likely been a mistake either in permissions, method parameters or ABI and contract address. Please go through the setup again.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/611278276ffe270af2a97644/file-rxfkptmQt8.png)

3\. If you are populating fractional numbers, add 18 zeros to the original value. For example, if you want to invoke **immediateTransfer** method that will transfer 10.5 tokens, you will have to input 10.5\*10^18 = 10500000000000000000 into the amount field.
