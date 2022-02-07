# Process Overview

Similarly to an operating system, Vocdoni also **runs processes**. An OS process traditionally starts with a system call to the kernel, requesting the execution of a program with flags and permissions.

A voting process looks familiar. An Ethereum transaction (syscall) is made to the [process smart contract](https://github.com/vocdoni/dvote-solidity#process) (kernel), with parameters that define how the election will behave. The transaction will include metadata, the root of the census and [dozens of flags](https://github.com/vocdoni/dvote-solidity#types-and-values) that allow to run processes with powerful features.

An oracle will relay the transaction with the same parameters (and signature) to the Voting blockchain. At this point, the process has been created on the Vochain and valid votes will be accepted from users who belong to the given census.

From a component's perspective, the system can be decoupled in three stages.

### Process creation <a href="#process-creation" id="process-creation"></a>

Using one of many [census integration methods](https://docs.vocdoni.io/architecture/census-overview.html), an organization publishes a Census Merkle Tree containing information about the eligible voters for a process. The organization then creates a process itself by pinning the metadata (including this census) to a decentralized filesystem and sending a transaction to the Voting Blockchain to persist the vote details.

![](<../../../../.gitbook/assets/image (9).png>)

### Voting <a href="#voting" id="voting"></a>

Users need to fetch the metadata of the process, choose the vote options and generate Merkle Proof to bundle a vote package. If the process is private, clients also need to fetch the public keys to use for vote encryption. If the process is anonymous, the user computes a [Zero Knowledge proof](https://docs.vocdoni.io/architecture/protocol/anonymous-voting/anonymous-voting.html).

The client submits a Vote envelope (containing the proof and the voting choices) to one or several Gateways. These are connected to the Vochain P2P network, so Gateways will relay the envelope to the blockchain mempool.

The Vochain nodes and miners validate the Census Merkle Proof or Zero Knowledge Proof. If valid, the vote package is added to the next block and becomes available for computing the results.

![](<../../../../.gitbook/assets/image (39).png>)

### Results <a href="#results" id="results"></a>

When an encrypted process ends, encryption keys are revealed by the [Keykeepers](https://docs.vocdoni.io/architecture/services/vochain.html#special-actors) so that scrutiny can take place. From this moment on, any node on the network can start counting and validating votes.

At the same time, an Oracle computes the results and submits them to the Process Smart Contract, so that results become available on-chain.

> For results on-chain, an Oracle could compute a Zk-Rollup of process results. This [proposal](https://docs.vocdoni.io/architecture/protocol/rollup.html#zk-rollups-proposal) effectively makes the Oracles trustless components and enables anti-coercive, verifiable and binding results on the Ethereum mainnet.\
> The ZK-Rollups functionality may require heavy computational resources and development time until it is available. For this reason, intermediary approaches like Optimistic Rollups may be implemented first and iterated upon later.>

![](<../../../../.gitbook/assets/image (4).png>)
