---
cover: ../../../../../.gitbook/assets/03.png
coverY: 0
---

# Tokens App

The Tokens app is used to **mint new tokens** and **assign** them to yourself or other entities. Tokens minted by the Tokens app **confer voting abilities** to holders of the tokens.

There are many reasons an organization might mint tokens for entities. Here are a few examples:

* The organization commits to giving its workers a stake in the company e.g. half of the company tokens are held by workers and the other half by investors .
* The organization mints tokens to entities proportional to the amount of funds they have invested in the company.
* The organization mints a specific amount of tokens for an entity in exchange for a specific good or service .
* The organization mints a fixed amount of tokens per month and distributes them proportionally to everyone who has contributed value to the organization that month.

The Tokens app is used to **manage membership** and **voting power** in an organization. To add members to an organization, it’s as easy as minting and assigning a token to them.

On the Company template, one token equals one vote, members can hold as many tokens as are assigned to them, and tokens are transferable.&#x20;

With the Membership template, one token also equals one vote, but members cannot hold more than one token each and tokens are non-transferable.&#x20;

Regarding the Reputation template, one token equals one vote, and members can hold as many tokens as are assigned to them, but the tokens are non-transferable.

This simple process for managing membership and voting power provides the foundation for governing the resources of an organization using Aragon.

![Tokens App](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d542c7d3a7e9ae174bd/file-3GPg0yG2o5.png)

## **Holder**

In the _Holder_ section of the _Tokens_ app, you can see the current list of token holders and the balance of organization tokens they each hold.&#x20;

Clicking on the dropdown menu on one of the rows in the list will provide you options for:

* Assigning more tokens to that token holder (_Add tokens_ option).&#x20;
* Removing tokens from the token holder (_Remove tokens_ option).
* Editing a custom label (for more about this go [here](../home.md)).

![Tokens app view](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867d622c7d3a7e9ae174be/file-dgpIXaBkm6.png)

## **Token Info**

In the _Token Info_ section you can see information about the token that is used for governance in your organization:

* _Token supply_: how many tokens have been minted in total
* _Transferable_: whether or not the token can be transferred to another entity after it has been assigned.
* _Token_: the token name and token symbol.

![Token info view](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867df22c7d3a7e9ae174bf/file-7fiikNO0jj.png)

## **Ownership Distribution**

In the _Ownership Distribution_ section, you can see which entities own what percent of the organization’s token supply. This can be helpful as a spot check to see how token ownership is concentrated in the organization.

![Ownership distribution](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867dff04286364bc8f65d9/file-nj7kpToblW.png)

## **Add Tokens**

If you need to add members to your organization and assign them DAO tokens, you need to use the _Add Token_ option.

If you click the _Add Tokens_ button, a panel will open up with text fields for entering:

* The _recipient_: the address of the entity you want to assign tokens to.&#x20;
* _Number of tokens_: how many tokens you want to assign.&#x20;

After you enter this information, you can click the _Add tokens_ button in the panel to finish completing the action.

![Add token](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d867e382c7d3a7e9ae174c0/file-gQIE902ZlX.png)

At this point, the organization still requires a tokenholder vote for every action. Click _Create transaction_ to create the transaction that creates a **new vote** to assign the new token you want to mint. Sign the transaction in your Ethereum provider, wait for a confirmation, then move on to the next step.



![](https://lh3.googleusercontent.com/RVlpE5QIyKb2gvvr5KQOf8ukZa0k5wczXfgOnnHfcvXI2JnBUtLX4KjKob\_EWMF9k9y1NjB1yzNcYrJLm2ETRezy7v9DDWucQNQ18OEQT\_8dBjMvSoZsymVIGK\_BJv\_8Cw1Mk88L)

### **Vote "Yes" to approve the "Assign Tokens" vote **<mark style="color:blue;">****</mark>&#x20;

Go to the Voting app, click on the _Mint tokens_ proposal you just created, and vote "Yes" to approve minting and assigning the token.

![](https://d33v4339jhl8k0.cloudfront.net/docs/assets/5c98a4fe0428633d2cf3fcf7/images/5d8a553504286364bc8f7fff/file-qb1DOKAI56.png)

![](https://lh6.googleusercontent.com/OYlBJ41umTMbdfMLqS9geT8ycshlmUfUgPHz6pNkg9cwIx3zNKAb8elnfw0QAKpo5N9rpah\_vExxl2lJYQG3ChtEK-5evFmrDG\_C92IUjn6\_Gt1\_WD8sP2ntGPaiVAeo4jZrQq1\_)

![](https://lh5.googleusercontent.com/IJWz3XKDtHi4MlsuxGlLJ8zatP6RiAluev6UK72zn1kMlHkpzNMAZEGyqSxw\_sp5lRIwHNU5ErZI1F0tjh\_8yVfIx99ImrR3X\_Xy7DWd9MC8k\_nY9w4X5CVbH6EqwnR54SD3kBw7)

![](https://lh6.googleusercontent.com/SJXCuLvpm6UwVIvBsplOQCcH5mfm11meFrHj9HRVH1FOGiM\_ax8Wmzf4IoQtX2GJNSDLC7BrUn8RmdDuaZ0Vzd9fhH\_JT-TggnudmR\_408oQ6VC6N6JWZXi1Hc2SudTl\_Y1p0xzZ)

### **Check out the newest member of your organization**

Your organization just went from one to two members. A good start to a new Company organization!

Note: If a vote is cast that causes the Approval % to be equal to or greater than the Support required (e.g. 60% required Support with current 65% Approval), then the proposition will be completed automatically. If the Approval % is less than the Support required (e.g. 60% required Support with current 40% Approval) then additional "no" votes could still stop the proposition from being passed. Thus the proposition will remain open until either the duration is reached or the  Approval % is equal to or greater than the Support requirement.&#x20;

![](https://lh4.googleusercontent.com/DOedZ-Oj8ettsh6BPRTs7e7aY9ubI8k\_1R9oYcVTdiDouLo3coVdYI4s8pGTtZdHqw65aS1JgJ4ZTdQT77Unz86R9BvorceFOaebefJP9u1UJ2pfMY71PPZEerI3uVcGD\_CW13UA)



> #### <mark style="color:purple;">Do you have a question? Leave your comments here at our Discourse forum</mark> 👇

{% embed url="https://aragontesting.trydiscourse.com/t/aragon-client-navigate-your-dao-token-app/26" %}
