# README

[**Website** ](https://aragon.org)**|** [**Documentation** ](https://docs.aragon.org/govern/)**|** [**Chat**](https://discord.gg/aragon)

![](<../../../.gitbook/assets/image (36).png>)****[ **** ![](<../../../.gitbook/assets/image (7).png>)](https://www.npmjs.com/package/@aragon/govern-core)[ ![](<../../../.gitbook/assets/image (17).png>)](https://img.shields.io/badge/solidity-%3E%3D%200.6.8-lightgrey)[ ![](<../../../.gitbook/assets/image (24).png>)](https://github.com/aragon/govern/actions?query=workflow%3ACI)[ ![](<../../../.gitbook/assets/image (37).png>)](https://github.com/aragon/govern/actions?query=workflow%3ACD)[ ![](<../../../.gitbook/assets/image (3).png>)](https://codecov.io/gh/aragon/govern)



Govern is Aragon's new Smart Contract system to manage unstoppable organizations on the blockchain in an efficient and decentralized manner. It's architectured using ERC3000, the up and coming governance standard.

**🚨 Security Review Status: pre-audit**

The code in this repository has **not** been audited.

**📚 Read the** [**documentation**](https://docs.aragon.org/aragon-govern/)

Read the documentation if you have any doubts about the high-level overview of Govern, or if you want to know more about how everything works under the hood.

**👋 Get started contributing with a** [**good first issue**](https://github.com/aragon/govern/labels/good%20first%20issue%20%F0%9F%8C%9E)

Before explaining how you can contribute, It's worth mentioning that we use `develop` branch as the default one. This makes it easier for us to have all the latest, development changes without affecting the current production version. Though, We don't use `release` branches to make the process a little bit easier !

* Pushing to `develop` branch via PR deploys changes to testing environments(currently only rinkeby).
* Pushing to `master` branch via PR from `develop` deploys changes to production servers(mainnet).
* Pushing to `master|develop` directly will be restricted to make sure the PR's are reviewed.
* Creating PRs end up in relation to `develop` by default.

Don't be shy to contribute even the smallest tweak. Everyone will be especially nice and helpful to beginners to help you get started!

### Structure

This repo uses Lerna and yarn workspaces to bootstrap itself, and is divided into multiple independent sub-packages:

* [`erc3k`](broken-reference): Aragon's reference implementation of [ERC3000](https://eips.ethereum.org/EIPS/eip-3000), the up and coming governance standard.
* [`Govern.js`](broken-reference): Govern's official JS wrapper for creating seamless DAO experiences.
* [`Govern Console`](broken-reference): No-frills, forkable, extensible power user / developer UI tool for interacting with and visualizing low level information about Govern DAOs. Available on [console.aragon.org](https://console.aragon.org).
* [`Govern Contract Utils`](broken-reference): Set of all libraries and utilities used by the core Govern contracts.
* [`Govern Core`](broken-reference): The core set of Aragon Govern contracts.
* [`Govern Create`](broken-reference): Set of templates used to create new Govern instances.
* [`Govern Discord`](https://github.com/aragon/govern/blob/master/packages/govern-discord/README.md): Govern-native Discord bot for DAOs.
* [`Govern Server`](broken-reference): Server powering Govern.js and the Govern API to enable Web2-like experiences for DAOs.
* [`Govern Subgraph`](broken-reference): Govern's official Subgraph, which tracks DAOs registered on the A1-deployed ERC3000Registry.

### Deployed instances

To use Govern, feel free to deploy your own registries and factories, but using the official registries ensures that our tooling will detect your organization properly.



**Mainnet**

* 📜 GovernRegistry: [`0xf2b7D096cd34F228A6413e276132C21D98b19882`](https://etherscan.io/address/0xf2b7D096cd34F228A6413e276132C21D98b19882)
* 🏭 GovernBaseFactory: [`0x8bF05ce17B30f8C73B06e49f67076f944687c967`](https://etherscan.io/address/0x8bF05ce17B30f8C73B06e49f67076f944687c967)

**Rinkeby**

* 📜 GovernRegistry: [`0xf46253ef29FaedAbf63AA8cA6c0A41CbbdC93948`](https://rinkeby.etherscan.io/address/0xf46253ef29FaedAbf63AA8cA6c0A41CbbdC93948)
* 🏭 GovernBaseFactory: [`0x46013753f3a02ab4239cA936632E6C6B39235CCE`](https://rinkeby.etherscan.io/address/0x46013753f3a02ab4239cA936632E6C6B39235CCE)



### Help shape Aragon Govern

* Discuss in [Aragon Forum](https://forum.aragon.org/tags/aragon-govern)
* Join the [Aragon Govern channel](https://discord.gg/DrKMbeY) on Discord.
