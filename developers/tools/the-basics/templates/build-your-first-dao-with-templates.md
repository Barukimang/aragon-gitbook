# Build your first DAO with Templates

## Environment setup <a href="#environment-setup" id="environment-setup"></a>

Before starting you need to check if you have already installed all these prerequisites:

* the right version of **node.js** (recommended`v12 LTS` version)
* **Metamask** web3 provider
* the **aragonCLI** (Aragon Command Line Interface)&#x20;
* the **Aragon Buidler plugin**

If you haven't already installed them or if you need more info about this go to the "_Enviroment Setup_" paragraph [here](../getting-started.md).

## Getting started <a href="#getting-started-with-templates-using-the-aragoncli" id="getting-started-with-templates-using-the-aragoncli"></a>

Now we are ready to build our DAO with the templates.

The [aragonCLI](../../aragoncli/) (>= v4.1.0) supports using templates to create a DAO to interact with the apps being developed.

To quickly get started developing your own templates:

```
npx create-aragon-app app
```

That command will create a new Aragon app project with a sample template in it ready to be used. The Template (under `contracts/Template.sol`) will create instances of a Token Manager, a Voting app and the [Counter example app ](../../guides/your-first-aragon-app.md)and will wire the permissions so incrementing the Counter requires a vote to pass in the Voting app.

In order to start the Aragon client with a DAO created by the template, execute:

```
npm run start:ipfs:template
```

When modifying the name of your contract or app name be sure to update those in `Template.sol` otherwise running the template will fail.

## &#x20;<a href="#contributing" id="contributing"></a>

{% hint style="info" %}
✏️ [_<mark style="color:purple;">**Contributing**</mark>_](https://github.com/aragon/hack/edit/master/docs/getting-started.md)_<mark style="color:purple;">****</mark>_
{% endhint %}
