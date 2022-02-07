# Zk-Rollups (proposal)

_Zk-Rollups (proposal) for anti-coercive, scalable and deterministic execution_

The approach mentioned above presents an attack vector that could allow for automated vote buying mechanisms, especially for high-stakes elections.

Before an election ends, a user could exhibit their vote to a third party in exchange for a bounty. A buyer would need users to prove that their vote is associated with a given nullifier on the Vochain. This would require the generation of another valid ZK-Proof with the same nullifier as the original vote, but with different contents than the original.

One solution to this problem is to make use of **ZK-Rollups** as a vote aggregation and mixing mechanism between voters and the blockchain. This would make it impossible for any third party to verify that a voter chose a specific option.

Under this proposal, voters submit their encrypted vote envelopes using the same zk-SNARKs circuit as before. But instead of a public blockchain, each envelope is sent to a Rollup Relay through a private transport channel (many could exist). The Rollup Relay then decrypts the aggregated vote envelopes, validates them and computes them in batches (i.e 15 envelopes at a time) to produce a second ZK-Proof. Such a proof can be verified given the list of nullifiers and the aggregated results of the batch. The new ZK-Proof and the results aggregate is what will be stored in a public blockchain, such as the Vochain or Ethereum.

In this scenario voters are able to verify that their vote has been processed. No outsider, however, can determine what choices were selected by a specific voter. At the same time, the election's traceability and transparency properties are preserved.

![](https://docs.vocdoni.io/zk-rollup-vocdoni.png)

**Notes:**

* In such scenario, the commitment and reveal keys of the previous schema are no longer necessary.
* The Rollup Relays could potentially exchange private messages in order to announce the nullifiers they are processing (to avoid collisions).
* Some tuning is still required on this proposal in order to enable elections to be kept "secret until the end", but this feature seems possible.
* The Rollup Relay network might be incentivized in order to achieve better distribution. A mechanism such as the one implemented on the Hermez.io protocol (based on bidding) might be adopted.
