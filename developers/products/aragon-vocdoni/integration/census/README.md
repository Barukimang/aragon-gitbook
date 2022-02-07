# Census

The Voting Protocol requires a [Census](https://docs.vocdoni.io/architecture/census/census-overview.html) to be created and published before an organization can host a voting process. The voting protocol itself accepts three main census integration methods:

* [on-chain](https://docs.vocdoni.io/integration/census/on-chain.html)
* [off-chain credential service provider](https://docs.vocdoni.io/integration/census/off-chain-csp.html)
* [off-chain Merkle tree](https://docs.vocdoni.io/integration/census/off-chain-tree.html)

Between the three of these census methods, an incredible range of use-cases and third-party integrations for voter eligibility management is possible. Furthermore, the flexibility of the voting protocol is designed to allow more census types to be easily added in the future.

When creating a voting process, the [Census Origin](https://docs.vocdoni.io/architecture/smart-contracts/process.html#census-origin) must be set to signify which type of census the process will use.
