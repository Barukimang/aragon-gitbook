---
description: What is Aragon and what does it do
---

# Getting started

## Up and running <a href="#up-and-running" id="up-and-running"></a>

Now that we've got you all excited, let's go through what you need to get started building with Aragon 😊

## Environment setup <a href="#environment-setup" id="environment-setup"></a>

### Node.js <a href="#nodejs" id="nodejs"></a>

First off, we need to be sure we have the right version of Node.js installed.

{% hint style="warning" %}
For compatibility across OS we recommend `v12 LTS` version.
{% endhint %}

To see which version of Node you have installed, from the command line run:

```
node -v
```

If you haven't a node installed or if you haven't the right version, you can download it [here](https://nodejs.org/en/download/).

For managing more than one version node on your machine, you can download and install the nvm Manager [here](https://github.com/nvm-sh/nvm).&#x20;

### Web3 provider <a href="#web3-provider" id="web3-provider"></a>

Next, we'll need what we call a [web3 provider](before-starting.md) to actually sign and send transactions to the Ethereum (or another) blockchain.

In general, if you have a hardware wallet, we recommend you use [Frame](https://frame.sh) as your web3 provider -- we'll go over how to do this in the[ tutorial](../guides/your-first-aragon-app.md) that follows.&#x20;

For now in this section, to interact with the **Aragon app** we'll be using Metamask. If you haven't please proceed with the installation of [Metamask](../../../users/products/set-up-metamask/).

### The aragonCLI <a href="#the-aragoncli" id="the-aragoncli"></a>

The aragonCLI (or Aragon Command Line Interface) is a tool used for complex interactions with DAOs, like installing a new app, granting permissions with specific parameters or executing transactions through the [Agent app](https://hack.aragon.org/docs/guides-use-agent).

Now install aragonCLI from the command line running:

```
npm i -g @aragon/cli
```

{% hint style="danger" %}
If you're having trouble with this step, you should take a look at the installing aragonCLI section of the t[roubleshooting guide](../guides/troubleshooting-and-faq.md). If that doesn't fix things, please don't hesitate to reach out to us [here](../../../aragon/aragon-values-finances-and-legal/communicating-values.md).
{% endhint %}

### The Aragon Buidler plugin <a href="#the-aragon-buidler-plugin" id="the-aragon-buidler-plugin"></a>

The [Aragon Buidler plugin](https://github.com/aragon/buidler-aragon) is a user-friendly tool for developing apps on top of Aragon. The plugin is automatically installed when using the boilerplate templates but we can suggest to install now with the following command:

```
npm i @aragon/buidler-aragon
```

## Quick start - Build your first DAO <a href="#quick-start" id="quick-start"></a>

In order to get up and running quickly, **we’ll build our first DAO** using some basic scaffolding. Just like real scaffolding in a construction site, when we talk about scaffolding in this context, we mean a simple prebuilt structure for your project, on top of which you can build the real one.

To create your first (scaffolded) DAO, from the command line run:

```
npx create-aragon-app first-dao.aragonpm.eth
```

{% hint style="warning" %}
Don't worry about fully understanding this line right now. Really. We'll cover that in the [tutorial ](../guides/your-first-aragon-app.md)coming up. Right now, you just need to know that the scaffolding relies on some generated code, magically created by the `create-aragon-app` command.
{% endhint %}

{% hint style="info" %}
If you're unsure what the difference is between `npx` and `npm`, we recommend you read through this [medium post](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) and this [stackoverflow post.](https://stackoverflow.com/questions/50605219/difference-between-npx-and-npm)
{% endhint %}

Now if you look at your terminal, you should see a five step process:

![\*](https://hack.aragon.org/docs/assets/check.svg) `Preparing initialization`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Cloning app template`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Preparing template`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Installing package dependencies`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Created new application first-dao.aragonpm.eth in first-dao.`

Once all 5 have ticks next to them, you should run the following:

```
cd first-dao
npm start
```

where:

* `cd first-dao`, just moves us into the directory where the scaffolded app was created.
* `npm start`, sets up everything for us in the background so we can quickly live test our DAO.

{% hint style="success" %}
If you've made it this far congrats 🤗. You've just created your first DAO! It’s running on your local network and as soon as it's ready it will open in your browser at [localhost:3000](http://localhost:3000)!
{% endhint %}

## Interacting with your first DAO <a href="#interacting-with-your-first-dao" id="interacting-with-your-first-dao"></a>

First of all on metamask:

* login to metamask (if not already logged)
* select the [Localhost 8545 network](../../../users/products/set-up-metamask/)&#x20;
* import the [12 words of the seed](../../../users/products/set-up-metamask/import-your-seed-wallet-in-metamask.md) (account mnemonic) listed on the terminal :arrow\_down:

![Account mnemonic - 12 words of seed](<../../../.gitbook/assets/Schermata 2022-03-16 alle 12.34.11.png>)

If it's not already open, open your browser at the localhost address shown in your terminal. It should look something like this:

```
frontend | You can now view the Aragon client in the browser.
frontend | App content: http://localhost:8001
frontend | Client:  http://localhost:3000/#/0x0D13999edC23D3475Ed3FE22a15Cc7828FeCD762/0xA1A7d254552BEB05f15522EeD93B54441E61d1d9
frontend | Watching changes on front end...
```

Once your browser is open at the right address, you should see a screen that looks like the one below.

![DAO Home](https://hack.aragon.org/docs/assets/getting-started-dao-1.png)

As you can see on the left, this DAO is made up of two Aragon apps:

* Home
* first-dao (Counter)

Right now, we're in the Home app. This app just displays a welcome message with no possible user interactions.

Click on first-dao to open up the (slightly) more interesting Counter app.

![Counter app](<../../../.gitbook/assets/Schermata 2022-03-16 alle 12.30.03.png>)

Right now the count is at 0. Let's increment it.

Note that incrementing the counter triggers a blockchain transaction that saves the new value to the chain. But before the transaction can be sent, we need to sign it (to prove it was us that really sent it).

Click on the + button, which opens a metamask transaction and sign it. For help on how to sign a transaction go [here](../../../users/products/set-up-metamask/sign-a-transaction-with-metamask.md).

After the transaction is completed, you should see Count: 1.

{% hint style="success" %}
Done! We hope you enjoyed that 😊!&#x20;
{% endhint %}

## Next steps <a href="#next-steps" id="next-steps"></a>

Now that you’ve built your first DAO, feel free to take a look at the docs. If you're interested in understanding things at a deeper level go ahead this tutorial.&#x20;

## :paperclip: Contributing <a href="#contributing" id="contributing"></a>

You should find that there is a light blue EDIT button in the top-right corner the page. This button is available on every page of the Aragon docs. If you feel like you can improve our documentation in any way, please don't hesitate to click on it!

If you don't have any programming experience or if this is your first time contributing to an open-source project, don't worry. We've created a [GitHub guide](https://github.com/aragon/hack/tree/master/docs-internal/github-guide.md) just for you 😊.

P.S. Before you submit any changes, make sure to read our [contribution guidelines.](https://github.com/aragon/hack/blob/master/CONTRIBUTING.md)



