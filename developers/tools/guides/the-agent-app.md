# The Agent app

{% hint style="success" %}
How to use Aragon Agent
{% endhint %}

## Installing Aragon Agent

### 1. Create a Company DAO <a href="#1-create-a-company-dao" id="1-create-a-company-dao"></a>

Before we start, you'll need to head over to [Aragon](https://rinkeby.aragon.org) and create a new DAO with the [company template](https://github.com/aragon/dao-templates/tree/master/templates/company).

If you're not sure how to do that, please have a look at [this section](https://help.aragon.org/article/30-create-a-new-company-organization).

The first thing you'll be asked to do is to [choose the network](https://help.aragon.org/article/4-about-aragon) for your organization. For the purposes of this guide we'll choose the **Ethereum Testnet (Rinkeby)**.

Later on, you'll be asked to [set three parameters](https://help.aragon.org/article/30-create-a-new-company-organization#set) for your organization -- the **support**, the **minimum approval %**, and the **vote duration**.

We'll go with the following (sensible) defaults:

* Support: 100%
* Min. Approval: 0%
* Duration: 168 hours (or 1 week)

### [ ](https://hack.aragon.org/docs/guides-use-agent#2-install-aragoncli)2. Install aragonCLI <a href="#2-install-aragoncli" id="2-install-aragoncli"></a>

The [aragonCLI](https://hack.aragon.org/docs/cli-intro) (Command Line Interface) is what we use to create, interact with, and develop Aragon apps.

If you haven't done so already, install it from NPM by running the following command:

`npm install -g @aragon/cli`

Hopefully, it installed successfully 😊.

If not, we recommend you take a quick look at the [installing aragonCLI](https://hack.aragon.org/docs/guides-faq.html#installing-aragoncli) section of our [troubleshooting guide](https://hack.aragon.org/docs/guides-faq.html#installing-aragonCLI). It should help diagnose and fix the problem 🧐.

If that still doesn't fix things 😟, please reach out to us in our Spectrum [App development channel](https://spectrum.chat/aragon/app-development). We're more than happy to help.

Note that aragonCLI v5.4.0 was the first version to [include support](https://blog.aragon.one/aragon-agent-beta-release/) for Agent.

If you're unsure which version of aragonCLI you have, run:

`aragon -v`

If your version number is less than `7.0.3`, or if it's been a while since you last installed the aragonCLI, we recommend you reinstall it (by running the `npm install` command above).

### 3. Install the Agent app <a href="#3-install-the-agent-app" id="3-install-the-agent-app"></a>

Now that we've installed aragonCLI 🎉, we're ready to install the [Agent app](https://blog.aragon.one/aragon-agent-beta-release/).

aragonCLI installs the [`aragon dao`](https://hack.aragon.org/docs/cli-dao-commands) commands. We use these to interact directly with our DAO from the command line. They're also available directly using the `dao` shortcut.

We'll use the the [`dao install`](https://hack.aragon.org/docs/cli-dao-commands#dao-install) command to install the Agent app.

`dao install` takes two arguments:

1. The address or [aragonID](https://github.com/aragon/aragon-id) name of an Aragon DAO.
2. The package name of an Aragon app published to [aragonPM](https://hack.aragon.org/docs/apm-intro) (for the Agent app this would be agent or agent.aragonpm.eth).

So in our case, to install the Agent app, we need to run:

```
dao install <your organization name> agent --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

You should see that after `dao install <your organization's name> agent` we pass in two [global options](https://hack.aragon.org/docs/cli-intro.html#global-options): `--environment` and `--ipfs-rpc`.

> Note: As an alternative to passing the `--ipfs-rpc` option, you can also choose to run `aragon ipfs start` in another terminal.

<details>

<summary>Tell me more about aragon ipfs and these global options.</summary>



</details>

**Note that, in the true spirit of democracy, this step will trigger a vote in the DAO, you'll need to vote **_**yes**_** to confirm the installation of the Agent app.** To confirm the vote:

1. Click on the **Voting** app icon in the left panel. You should see you have one open vote.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-0.png)

1. Click on the **View vote** button. You should see a panel pop up on the right hand side.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-1.png)

1. Scroll to the bottom of the panel and click on the big green **Yes** button.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-2.png)

1. Sign the transaction with your favourite [web3 provider](https://hack.aragon.org/docs/getting-started.html#web3-provider) and voila! That's all there is to it. When you click on the Voting app again you should see the vote has passed with a 100% Yes vote.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-3.png)

### [ ](https://hack.aragon.org/docs/guides-use-agent#4-set-permissions)4. Set permissions <a href="#4-set-permissions" id="4-set-permissions"></a>

If you look at the end of the output of the `dao install` command you ran in the previous step, you should see something like:

```
↓ Fetching deployed app [skipped]
    → App wasn't deployed in transaction.
ℹ Successfully executed: "Execute desired action as a token holder"
 ⚠ After the app instance is created, you will need to assign permissions to it for it appear as an app in the DAO
```

What does this mean exactly 😕?

It's telling us that although we've successfully installed the Agent app, before we can use it as part of our DAO we need to define who can access the app's functionality.

In other words, we need to define who (or which app) has permission to execute actions in the Agent app and who can re-grant and revoke that permission.

In this guide we're going to give the Voting app permission to use the Agent app to execute actions.

To assign these permissions we need to get a hold of the Ethereum address of the Agent app -- remember **Agent is a fully-fledged Ethereum account** -- as well as the address of the Voting app in our DAO.

The Agent app address can be found by running the [`dao apps`](https://hack.aragon.org/docs/cli-dao-commands#dao-apps) command.

`dao apps` takes one argument: the address or name of an aragon DAO.

By default it only returns apps with permissions. But we can use the `--all` option to get it to return apps without permissions.

From the command line run:

`dao apps <your organization name> --all --environment aragon:rinkeby`

You should see a table that looks something like this:

| App                  | Proxy address                                  | Content                                             |
| -------------------- | ---------------------------------------------- | --------------------------------------------------- |
| kernel               | 0xa25fb31870bc492d450012ae32dafa72af9e82c3     | (No UI available)                                   |
| acl                  | 0xfefb0cdb7a1fac257815d52ba82776f98dc70205     | (No UI available)                                   |
| evmreg               | 0x9087db02300ef24b116daf0426b6ba22b28a0c79     | (No UI available)                                   |
| voting@v2.0.4        | **0x15a102f80ea3b1bd585a044e9b3c39a84c5f44e5** | ipfs:QmPjWU51opgTVnXwAhYAWasL2CaiYHqy2mXdXtzqfC8sKx |
| vault@v3.0.1         | 0x952a18185da912984e0bc8a830ba98f8151976af     | ipfs:QmeMabCnkA5BtTTszqqRztYKCXZqE9VQFH4Vx7dY9ue2nA |
| finance@v2.0.5       | 0x4171f7ac1a4606b93093e8648e2f9a16c59cf3b1     | ipfs:QmeMLs4jHya89khHVSubLaao9cZW6ELZUoYPHkwCUwKBH7 |
| token-manager@v2.0.3 | 0xbf07e1c74a72aa60df3ddf3115d15575d27e61e1     | ipfs:Qmb9Bv3J9AuXD5auY1WNwiJeohnYRhyso7XMULs7EZ8eTG |

Followed directly by another that looks like this:

| Permissionless app | Proxy address                                  |
| ------------------ | ---------------------------------------------- |
| agent              | **0x843bfA21a040E742ec32b8F6991e182D9655AF21** |

The permissionless app is the Agent app we've just installed. Its address is listed under **Proxy address** in the bottom table. In this guide that's **0x843bfA21a040E742ec32b8F6991e182D9655AF21** . Yours will be slightly different.

You should see that you can also find your Voting app's address by looking up the **Proxy address** of the voting app in the first table. In this guide that's **0x15a102f80ea3b1bd585a044e9b3c39a84c5f44e5** . Again, yours will be slightly different.

Another way you can find your Voting app's address is to use the UI:

1. Click on **App Center** in the left panel to see your installed apps.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-15.png)

1. Click on the **View details** button under the voting app.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-16.png)

1. Click on the blue box under **Installed intances** (see inside the red ellipse in the image below).

![](https://hack.aragon.org/docs/assets/agent-guide/agent-17.png)

1. You should see a small pop up appear with a header that says **Address**. Under the header is the address of your voting app. It should look something like **0x15a102f80ea3b1bd585a044e9b3c39a84c5f44e5**.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-18.png)

> Note: the above process works with any permissioned app!

Once you've located your Agent and Voting app addresses, run the following command to give your Voting app permission to use the Agent app to execute actions.

```
dao acl create <your organization name> <your agent app address> EXECUTE_ROLE <your voting app address> <your voting app address> --environment aragon:rinkeby
```

You should see the following output:

```
✔ Generating transaction
  ✔ Sending transaction
 ✔ Successfully executed
```

😊🎉 🎉😊



<details>

<summary>Tell me more about dao acl create.</summary>

Note that, same as before, this command will trigger a vote in the DAO and **you'll need to vote **_**yes**_** to confirm the new permissions you've granted the Voting app.**

You can do this either by using the Aragon client again or, now that you know how to get the address of your apps, by running:

```
dao exec <your organization name> <your voting app address> vote <vote id> true true --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/Note that, same as before, this command will trigger a vote in the DAO and you'll need to vote yes to confirm the new permissions you've granted the Voting app.

You can do this either by using the Aragon client again or, now that you know how to get the address of your apps, by running:

dao exec <your organization name> <your voting app address> vote <vote id> true true --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

</details>

<details>

<summary>Tell me more about dao exec.</summary>

[`dao exec`](https://hack.aragon.org/docs/cli-dao-commands#dao-exec) is used to perform transactions in your DAO directly from the aragonCLI. It takes at least three arguments:

* The first is always the name or address of the DAO you want to interact with. In our case this is our DAO's name.
* The second is the address of the app where the action is being performed. In our case this is the [Voting app](https://help.aragon.org/article/19-voting).
* The third is the name of the method being executed in the app: In our case the method is [`vote`](https://github.com/aragon/aragon-apps/blob/master/apps/voting/contracts/Voting.sol#L154).
* The remaining arguments are the arguments which the method -- in our case `vote` -- will be executed with. We are passing in three: `1`, `true` and `true`.
  * The first (`1`) is the id for the vote we want to interact with. This is always an integer. Vote ids start at 0 and increment by 1 each time a vote is created.
  * The second (`true`) specifies which way we want to vote: `true` means yes and `false` means no.
  * And the third (`true`) specifies whether the contract should check if a vote already has enough support to be executed. If it does, the Voting app will perform the action that was being voted on, and the vote will be close. `true` means check if this vote can be executed, `false` means don't check.

</details>



![](https://hack.aragon.org/docs/assets/agent-guide/agent-4.png)

> Tip: If you need to look up the id of a vote, look the vote up in the Voting app UI. You'll find the id in the top left corner (next to the hashtag). For example in the image above, the id of the vote is 1 (look inside the red circle).

### [ ](https://hack.aragon.org/docs/guides-use-agent#5-check-permissions) <a href="#5-check-permissions" id="5-check-permissions"></a>

### 5. Check permissions

As a final step, let's verify that permissions have been set properly through the UI:

1. Click on the **Permissions** menu option in the left panel. You should see the Agent app at the end of the second row. Click on it.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-5.png)

1. Under **Actions available on this app** should see that the Voting app now manages who has the ability to execute actions for the Agent app. Scroll down.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-6.png)

1. Under **Permissions set on this app** you should see that Voting app now has permission to use the Agent app to execute actions. 🎉🎉🎉

![](https://hack.aragon.org/docs/assets/agent-guide/agent-7.png)

## Interacting with Aragon Agent <a href="#interacting-with-aragon-agent" id="interacting-with-aragon-agent"></a>

### Introducing dao act <a href="#introducing-dao-act" id="introducing-dao-act"></a>

`dao act` is the main way we'll interact with Aragon Agent. It's the command we use to perform transactions with the Agent app directly from aragonCLI.

According to the documentation:

> `dao act` provides some syntax sugar over `dao exec` for executing actions using Agent app instances in a DAO.

Like `dao exec` it takes at least three arguments:

1. The address of the Agent app you want to use to perform an action.
2. The address of an **external contract** or **the address of an app** within a DAO.
3. The [full signature](https://www.4byte.directory) of the method we wish to execute in either the external contract or the app we specified in the second arugument -- note that by the full signature we mean the [human readable function signature](https://solidity.readthedocs.io/en/v0.5.3/abi-spec.html#function-selector).

> For example if we wanted to execute the `vote` method of a Voting app we would pass in its full signature `vote(unint256,bool,bool)` as the third argument. And if we wanted to execute the `confirmTransaction` method of a [Gnosis Multisig](https://wallet.gnosis.pm/#/wallets) we would pass in `confirmTransaction(uint256)`.

The remaining arguments are the parameters which the method we specified will be executed with.

Don't worry if it's not completely clear to you how `dao act` works at this stage. The following use cases will help you develop some intuition for it!

### Use case: Voting in another organization <a href="#use-case-voting-in-another-organization" id="use-case-voting-in-another-organization"></a>

Let's start by seeing how we can use the Agent app to allow one Aragon organization to participate as a stakeholder in another.

#### 1. Create another Democracy DAO <a href="#1-create-another-democracy-dao" id="1-create-another-democracy-dao"></a>

The first step is to create another Democracy DAO. Exactly the same as before, head over to [Aragon](https://rinkeby.aragon.org) and choose the following defaults:

* Support: 100%
* Min. Approval: 0%
* Duration: 168 hours (or 1 week)

#### 2. Mint a token to allow our first DAO (A) to vote in our new DAO (B) <a href="#2-mint-a-token-to-allow-our-first-dao-a-to-vote-in-our-new-dao-b" id="2-mint-a-token-to-allow-our-first-dao-a-to-vote-in-our-new-dao-b"></a>

We've now created two Democracy DAOs -- let's call them **A** and **B**. A has an Agent app, B doesn't. We want to allow A to vote in B.

Remember that A needs to be a tokenholder of B to be able to vote in B. And that A's Agent app acts its external interface.

In other words, A's Agent app allows it to participate as a stakeholder in B.

This means that to allow A to vote in B we need to mint a token for A's Agent app in B.

To do this run:

```
dao exec <name of dao B> <token manager app address of dao B> mint <agent app address of dao A> 1000000000000000000 --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

Remember, you can find the addresses of the apps in any of your DAOs by running `dao apps <organization name> --environment aragon:rinkeby`.

As you can see, we are using the `dao exec` command to interact with the `mint` method of B's [Token Manager](https://help.aragon.org/article/18-tokens) app.

[`mint`](https://github.com/aragon/aragon-apps/blob/master/apps/token-manager/contracts/TokenManager.sol#L104) is used to create new tokens and assign them to a receiver. It takes two arguments: a receiver address and the amount of tokens to be created.

In our case the receiver is A's Agent App, and the amount of tokens to be created is 1.

However, you should notice that instead of writing `1` as the second argument to `mint` we've gone with `1000000000000000000`.

This is because the token created by the [company template](https://github.com/aragon/dao-templates/tree/master/templates/company) has 18 decimals, so 1 unit of a token is actually 0.000000000000000001 tokens. This is not what we want.

In order to mint a full token from the CLI we need to pass the full number, which will then be interpreted with 18 decimals. In our case this is a 1 followed by eighteen 0s, or `1000000000000000000`.

> Note: If you're having problems with this step, you might need to run [`aragon ipfs`](https://hack.aragon.org/docs/cli-ipfs-commands#aragon-ipfs) in another terminal.

Finally, the usual warning: running the above command will trigger a vote in B to create and send a token to A's Agent App: we'll need to vote _yes_ to confirm the minting of the token.

You can do this either directly through the UI or by running:

```
dao exec <name of dao B> <voting app address of dao B> vote 0 true true --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

On the UI, the vote will look something like this.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-8.png)

Once you've voted _yes_, switch over to the Token Manager app (click on **Tokens** in the left sidebar).

![](https://hack.aragon.org/docs/assets/agent-guide/agent-9.png)

You should see that you've successfully added another token holder (your Agent app)! 🎉🎉😊

#### 3. Create a vote in B to add a third entity <a href="#3-create-a-vote-in-b-to-add-a-third-entity" id="3-create-a-vote-in-b-to-add-a-third-entity"></a>

As in step 2, we'll run `dao exec` again, except this time the first argument to `mint` will be the address of the third entity we want to add to B.

```
dao exec <name of dao B> <token manager app address of dao B> mint <third entity's address> 1000000000000000000 --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

Running the above will create an open vote in B. Again we'll need to vote _yes_ to confirm the minting.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-10b.png)

As before, you can either do this through the UI or run the same command we ran at the end of step 2 with one small modification:

This time the first argument to `vote` will be a `1` and not a `0`, since the id of this new vote is 1. Remember that vote ids start at zero and increment by one each time a vote is created.

If you go to the Voting app after you've voted, you'll see that the _yes_ vote is only 50%.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-10.png)

That's because only one out of two token holders have voted. The other token holder (A's Agent app) still has to vote.

#### 4. Use A's Agent app to take part in B's vote <a href="#4-use-a-s-agent-app-to-take-part-in-b-s-vote" id="4-use-a-s-agent-app-to-take-part-in-b-s-vote"></a>

In order to close and enact the vote, we'll use A's Agent app to vote yes to adding a third entity to B.

To do this we need to use the `dao act` command we introduced at the beginning of this section.

Remember that `dao act` takes at least three arguments:

* The first is the address of the Agent app you want to use to perform an action. In our case this is the address of A's Agent app.
* The second is the address of an **external contract** or the address of an app within a DAO. In our case this is the address of B's [Voting app](https://help.aragon.org/article/19-voting).
* The third is the [full signature](https://developer.mozilla.org/en-US/docs/Glossary/Signature/Function) of the method we wish to execute in either the external contract or the app we specified in the second argument. In our case the method is [`vote`](https://github.com/aragon/aragon-apps/blob/master/apps/voting/contracts/Voting.sol#L154) and its full signature is `vote(unint256,bool,bool)`.
* Finally, the remaining arguments are the arguments which the method -- in our case `vote` -- will be exectuted with. We can see from the signature that `vote` takes three arguments: an interger, a boolean, and a boolean. In our case we will pass in: `1`, `true` and `true`.
  * The first (`1`) is the id for the vote we want to interact with. This is always an integer. Remember that vote ids start at 0 and increment by 1 each time a vote is created.
  * The second (`true`) specifies which was we want to vote: true means yes and false means no.
  * And the third (`true`) specifies whether the contract should check if a vote already has enough support to be executed. If it does, the Voting app will perform the action that was being voted on, and the vote will be close. `true` means check if this vote can be executed, `false` means don't check.

So in our case, we run:

```
dao act <agent app address of dao A> <voting app address of dao B>  "vote(uint256,bool,bool)" 1 true true  --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

The result of this command will be to trigger a vote in A on whether to allow A's Agent app to execute the vote in B.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-11.png)

#### 5. Confirm the vote/action in A <a href="#5-confirm-the-vote-action-in-a" id="5-confirm-the-vote-action-in-a"></a>

The final step is to confirm the vote in A.

Again, we can do this either through the UI or by running:

```
dao exec <name of dao A> <voting app address of dao A> vote 2 true true --environment aragon:rinkeby --ipfs-rpc https://ipfs.eth.aragon.network/ipfs/
```

Note that we passed in a vote id of `2` as the first argument to `vote`. That's because this is the third vote created in A, and vote ids start at 0.

Once you've confirmed the vote, if you head over to B's voting app again you should see that the vote to mint one token for your chosen third entity now has 100% support.

![](https://hack.aragon.org/docs/assets/agent-guide/agent-13.png)

Finally, to double check that your chosen entity has really been added as a stakeholder in B, click on B's Token Manager (named **Tokens** in left panel).

![](https://hack.aragon.org/docs/assets/agent-guide/agent-14.png)

You should see there are now three tokenholders, each with equivalent stakes.

If you've made it this far, congratulations! 😊🎉😊🎉

You've just used the Agent app to allow one Aragon organization to participate as a stakeholder in another!

On next iteration of this guide we will explain 3 new use cases:

1. Interacting with Compound
2. Creating an Aragon Trust
3. Opening a Maker CDP

Stay tuned!

## Further resources <a href="#further-resources" id="further-resources"></a>

* [Dynamic Permissions for Organization “Actions” with Signer Integration](https://forum.aragon.org/t/dynamic-permissions-for-organization-actions-with-signer-integration/116)
* [Agent app, arbitrary actions from DAOs](https://forum.aragon.org/t/agent-app-arbitrary-actions-from-daos/275)
* [Releasing Aragon Agent beta](https://blog.aragon.one/aragon-agent-beta-release/)

