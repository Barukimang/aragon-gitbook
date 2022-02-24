---
cover: ../../../.gitbook/assets/03.png
coverY: 0
---

# Create a DAO from Template

> _Note: Make sure you have all of the_ [_prerequisites_](https://help.aragon.org/article/90-prerequisites) _before proceeding with this guide_

## <mark style="color:purple;">**2.1.1 Navigate to**</mark> [<mark style="color:purple;">**app.aragon.org**</mark>](https://app.aragon.org) <mark style="color:purple;">**in your web browser**</mark>

Enable your account, select which network you want to use to create your organization, then click "Create an organization".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d826d982c7d3a7e9ae152a1/file-sTnfeEGIqe.png)

## <mark style="color:purple;">**2.1.2 Select the “Company” template**</mark>

A “Company” organization that uses transferable tokens to represent stake in the company. Decisions are made using token-weighted voting, where one token equals one vote.

Click "View details", review the apps available, check the boxes to install any optional apps you want to install

When finished, click "Use this template".

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d826f0204286364bc8f463b/file-AgyjSpxvPa.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86242f04286364bc8f6507/file-QeXiahqUec.png)

## <mark style="color:purple;">**2.1.3 Claim a name then click “Next”**</mark>

Aragon uses the [Ethereum Name Service](https://ens.domains) (ENS) to assign names to organizations.

_Note: The organization's ENS name currently cannot be changed._

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86243e04286364bc8f6508/file-Z2F9ilkt9Z.png)

## _<mark style="color:purple;">**2.1.4 Configure the parameters of the Voting app**</mark>_

_Note: The Voting app parameters currently cannot be changed from the Aragon frontend client. To change the Voting app parameters after your organization has been created, you must first initialize the permissions to change these parameters, then you can change the parameters using the_ [_aragonCLI_](https://hack.aragon.org/docs/cli-intro.html)_._

#### _Support_

_"Support" is the relative percentage of tokens that are required to vote “Yes” for a proposal to be approved. For example, if “Support” is set to 50%, then more than 50% of the tokens used to vote on a proposal must vote “Yes” for it to pass._

#### _Minimum Approval_

_"Minimum Approval" is the percentage of the total token supply that is required to vote “Yes” on a proposal before it can be approved. For example, if the “Minimum Approval” is set to 20%, then more than 20% of the outstanding token supply must vote “Yes” on a proposal for it to pass._

#### _Vote Duration_

_“Vote Duration” is the length of time that the vote will be open for participation. For example, if the Vote Duration is set to 24 hours, then tokenholders have 24 hours to participate in the vote. After the vote duration time has elapsed, if the vote does not meet the Minimum Approval or Support requirements, then it will automatically fail. Otherwise, the vote will be passed. This parameter cannot be changed after the organization is created._

\\

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d86246d04286364bc8f6509/file-gNMrRn48K4.png)

## _<mark style="color:purple;">**2.1.5 Choose a token name and symbol and add tokenholders**</mark>_

_Note: The token name and symbol currently cannot be changed. Do not add more than a few tokenholders to your organization on this screen or the transaction to create your organization may fail; you can add more tokenholders after the organization has been created._

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624862c7d3a7e9ae173e4/file-wSKI8WfAzK.png)

## _<mark style="color:purple;">**2.1.6 Review organization information**</mark>_

_Open each panel to make sure that the information entered to launch your organization is correct. If anything is incorrect, you can click the "back" button to return to an earlier screen and make the necessary correction_

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624af04286364bc8f650a/file-QLxk1Q0FZj.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624b704286364bc8f650b/file-IsP1SOVaHO.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624bf2c7d3a7e9ae173e5/file-Qn8KEkg3If.png)

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624c604286364bc8f650c/file-Fqvyo6L3Kz.png)

## <mark style="color:purple;">**2.1.7 Launch your organization**</mark>

_Now you need to sign a transaction to create your organization. Open your Ethereum provider if the window does not open automatically. Click the "confirm" button in your Ethereum provider to sign and broadcast the transaction._

\\

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624d704286364bc8f650d/file-arEtXF8S0j.png)

## <mark style="color:purple;">**2.1.8 Click "Get started"**</mark>

_Your new Company organization is ready to go!_

_Now you can_ [_explore your new Company organization_](https://help.aragon.org/article/31-explore-the-company-organization)_._

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8624ee04286364bc8f650e/file-a4bAYgLmxU.png)
