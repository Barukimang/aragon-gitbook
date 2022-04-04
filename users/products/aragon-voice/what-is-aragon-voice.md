# What is Aragon Voice?

****[**Aragon Voice**](https://voice.aragon.org) **** is a new gasless and universally verifiable voting solution for submitting proposals for any ERC20 token and voting on them using a decentralized end-to-end verifiable protocol.

## Anyone with an Ethereum address can:

* Design and implement **on-chain proposals** for their ERC20 project, where **votes** can be cast **without gas fees**, and are recorded as metadata both to Ethereum and IPFS.&#x20;
* Signal proposals that use a centralized backend but are universally verifiable\* on our custom vote-counting blockchain (Vochain).&#x20;

> \* from process creation to vote recount, every operation is transparent and can be freely audited by a third party. Voters themselves can also check that their vote has been counted properly using their ballot receipt to query the [Vochain explorer](https://explorer.vote).

{% hint style="warning" %}
Only on-chain proposal creators need to pay the gas costs of deploying the information to the mainnet. The votes can be cast without gas fees.&#x20;
{% endhint %}

Proposals are processed on Vochain (Aragon's layer 2 protocol) and vote metadata is stored on IPFS.&#x20;

## **Vocdoni OpenStack**

To power Aragon Voice, we are using the Vocdoni OpenStack: **a fully anonymous voting protocol by design, ensuring data availability and censorship-resistant protocol communication**.&#x20;

This technology is also the base for Vochain, a layer-2 (L2) voting-specific blockchain, used for accounting ballots transparently.

The result is a completely permissionless, decentralized, and highly scalable governance solution for DAOs and other initiatives that make use of ERC20 tokens.

{% hint style="info" %}
Aragon Voice can be used for permissionless signaling, dispute resolution and deterministic on-chain execution when combined with Aragon Court and Aragon Govern.
{% endhint %}
