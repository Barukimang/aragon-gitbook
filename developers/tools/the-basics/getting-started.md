---
description: What is Aragon and what does it do
---

# Getting started

## Up and running <a href="#up-and-running" id="up-and-running"></a>

Now that we've got you all excited, let's go through what you need to get started building with Aragon 😊

### Environment setup <a href="#environment-setup" id="environment-setup"></a>

#### Node.js <a href="#nodejs" id="nodejs"></a>

First off, we need to be sure we have a recent version of Node.js installed, for compatibility across OS we recommend LTS (`v12`) version.

To see which version of Node you have installed, from the command line run:

```
node -v
```

To download node, [follow this link](https://nodejs.org/en/download/).

#### Web3 provider <a href="#web3-provider" id="web3-provider"></a>

Next, we'll need what we call a web3 provider to actually sign and send transactions to the Ethereum blockchain.

If you're new to the decentralized web you might be wondering why we have to use a separate provider to interact with the blockchain. Why don't decentralized apps (like Aragon's) just do it themselves?

In short, while it's possible for dapps to interact directly with the blockchain, using a web3 provider allows users to interact with dapps without trusting every one of them with their private keys (the keys to theirs funds).

Without a web3 provider, users have to have total trust in every dapp they use. With a web3 provider, they just need to trust that provider.

> In general, if you have a hardware wallet, we recommend you use [Frame](https://frame.sh) as your web3 provider -- we'll go over how to do this in the [tutorial](https://hack.aragon.org/docs/tutorial.html) that follows. To interact with the app in this section however, we'll be using [Metamask](https://metamask.io).

**Metamask**

MetaMask is a browser plugin that allows users to make Ethereum transactions through regular websites. It does this by injecting a javascript library called web3.js into the namespace of each page your browser loads.

web3.js is written by the Ethereum core team, and has functions that regular webpages can use to make read and write requests to the blockchain. Eventually we'll have browsers with this sort of functionality built-in. But for now we need plugins like Metamask to help us bridge the gap between web2 and web3.

For instructions on how to use Metamask as your web3 provider, please follow our [Metamask guide](https://hack.aragon.org/docs/guides-use-metamask.html).

#### The aragonCLI <a href="#the-aragoncli" id="the-aragoncli"></a>

The aragonCLI (or Aragon Command Line Interface) is a tool used for complex interactions with DAOs, like installing a new app, granting permissions with specific parameters or executing transactions through the [Agent app](https://hack.aragon.org/docs/guides-use-agent).

To install aragonCLI from the command line run:

```
npm i -g @aragon/cli
```

If you're having trouble with this step, you should take a look at the installing aragonCLI section of the [troubleshooting guide.](https://hack.aragon.org/docs/guides-faq#installing-aragonCLI) If that doesn't fix things, please don't hesitate to reach out to us in the [SDK Working Group channel](https://spectrum.chat/aragon/sdk-working-group).

#### The Aragon Buidler plugin <a href="#the-aragon-buidler-plugin" id="the-aragon-buidler-plugin"></a>

The [Aragon Buidler plugin](https://github.com/aragon/buidler-aragon) is a user-friendly tool for developing apps on top of Aragon. The plugin is automatically installed when using the boilerplate templates but can be added to any project with the following command:

```
npm i @aragon/buidler-aragon
```

### Quick start <a href="#quick-start" id="quick-start"></a>

In order to get up and running quickly, we’ll build our first DAO using some basic scaffolding. Just like real scaffolding in a construction site, when we talk about scaffolding in this context, we mean a simple prebuilt structure for your project, on top of which you can build the real one.

To create your first (scaffolded) DAO, from the command line run:

```
npx create-aragon-app first-dao.aragonpm.eth
```

Don't worry about fully understanding this line right now. Really. We'll cover that in the [tutorial](https://hack.aragon.org/docs/tutorial.html) coming up. Right now, you just need to know that the scaffolding relies on some generated code, magically created by the `create-aragon-app` command.

If you're unsure what the difference is between `npx` and `npm`, we recommend you read through this [medium post](https://medium.com/@maybekatz/introducing-npx-an-npm-package-runner-55f7d4bd282b) and this [stackoverflow post.](https://stackoverflow.com/questions/50605219/difference-between-npx-and-npm)

If you look at your terminal, you should see a five step process:

\


![\*](https://hack.aragon.org/docs/assets/check.svg) `Preparing initialization`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Cloning app template`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Preparing template`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Installing package dependencies`

![\*](https://hack.aragon.org/docs/assets/check.svg) `Created new application first-dao.aragonpm.eth in first-dao.`

\


Once all 5 have ticks next to them, you should run the following:

```
cd first-dao
npm start
```

The first line, `cd first-dao`, just moves us into the directory where the scaffolded app was created.

And the second, `npm start`, sets up everything for us in the background so we can quickly live test our DAO.

If you've made it this far congrats 🤗. You've just created your first DAO! It’s running on your local network and as soon as it's ready it will open in your browser at [localhost:3000](http://localhost:3000)!

#### Interacting with your first DAO <a href="#interacting-with-your-first-dao" id="interacting-with-your-first-dao"></a>

If it's not already open, open your browser at the localhost address shown in your terminal. It should look something like this:

```
frontend | You can now view the Aragon client in the browser.
frontend | App content: http://localhost:8001
frontend | Client:  http://localhost:3000/#/0x0D13999edC23D3475Ed3FE22a15Cc7828FeCD762/0xA1A7d254552BEB05f15522EeD93B54441E61d1d9
frontend | Watching changes on front end...
```

Once your browser is open at the right address, you should see a screen that looks like the one below.

![](https://hack.aragon.org/docs/assets/getting-started-dao-1.png)

As you can see on the left, this DAO is made up of two Aragon apps -- Home and Counter. Right now, we're in the Home app. This app just displays a welcome message with no possible user interactions.

Click on Counter to open up the (slightly) more interesting Counter app.

![](https://hack.aragon.org/docs/assets/getting-started-dao-2.png)

Right now the count is at 0. Let's increment it.

Note that incrementing the counter triggers a blockchain transaction that saves the new value to the chain. But before the transaction can be sent, we need to sign it (to prove it was us that really sent it).

**Signing your first transaction with Metamask**

To sign your first transaction with Metamask, head to the **Signing your first transaction with Metamask** section of our [Metamask guide](https://hack.aragon.org/docs/guides-use-metamask.html#signing-your-first-transaction-with-metamask).

### Next steps <a href="#next-steps" id="next-steps"></a>

We hope you enjoyed that 😊! Please don't hesitate to leave us any feedback on [Spectrum](https://spectrum.chat/aragon/app-development).

Now that you’ve built your first DAO, feel free to take a look at the docs. If you're interested in understanding things at a deeper level, we recommend you jump straight into our [awesome tutorial](https://hack.aragon.org/docs/tutorial.html).

### Contributing <a href="#contributing" id="contributing"></a>

You should find that there is a light blue EDIT button in the top-right corner the page. This button is available on every page of the Aragon docs. If you feel like you can improve our documentation in any way, please don't hesitate to click on it!

If you don't have any programming experience or if this is your first time contributing to an open-source project, don't worry. We've created a [GitHub guide](https://github.com/aragon/hack/tree/master/docs-internal/github-guide.md) just for you 😊.

P.S. Before you submit any changes, make sure to read our [contribution guidelines.](https://github.com/aragon/hack/blob/master/CONTRIBUTING.md)
