---
cover: ../../../.gitbook/assets/04.png
coverY: 0
---

# Funds accidentally sent to an Aragon app address

If you accidentally sent tokens to the address of an app installed in an Aragon organization, you can recover the tokens and send them to the organization's Vault by following these steps:

1. [Install the aragonCLI](https://hack.aragon.org/docs/cli-intro.html) which is a command line interface for interacting with Aragon organizations.
2. Run `aragon ipfs` in your Terminal in order to provide aragonCLI with a way to access data (e.g. ABIs) for Aragon organizations.
3. [Set a private key for the aragonCLI to use](https://hack.aragon.org/docs/guides-faq#set-a-private-key), then send some ether to the address for this private key to pay for gas.
4. Send the following transaction command from the aragonCLI, replacing each "address" with the corresponding address relevant to your stuck transaction:

```powershell
dao exec OrganizationAddress AppAddress recoverToVault TokenContractAddress --environment aragon:mainnet
```

Where the `OrganizationAddress` __ is the address of the organization housing the stuck funds, the `AppAddress` is the address of the app you sent the stuck funds to, and the `TokenContractAddress` is the address of the token contract for the token you sent.

For example, if you sent [Dai](https://etherscan.io/token/0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359) to the Finance app address of the [genesis.aragonid.eth](https://mainnet.aragon.org/#/genesis/settings) organization, then the transaction command you would send to from the aragonCLI would be:

```
dao exec 0x8A83D4bCE45b4C4F751f76cf565953D1E4A3BF0a 0x98516C82Bda8B3dE6E2670B718848949Ae6a4643 recoverToVault 0x89d24A6b4CcB1B6fAA2625fE562bDD9a23260359 --environment aragon:mainnet
```

Thanks to Chris Hobcroft for documenting these steps in [this GitHub comment](https://github.com/ethereum-cat-herders/funding/issues/2#issuecomment-477174751).
