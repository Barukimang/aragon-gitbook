# The Census

In Vocdoni, a census of identities can be represented in one of three ways. For Ethereum-based processes, in which eligible voters are represented by Ethereum addresses holding a specific token, an [on-chain](https://docs.vocdoni.io/architecture/census/on-chain.html) (ERC-20) census is used. In cases where a central authority wants to manually validate each voter at the time of voting, [off-chain credential service provider](https://docs.vocdoni.io/architecture/census/off-chain-csp.html) is used. For all other voting processes (organizations that are not represented as DAOs), an [off-chain tree](https://docs.vocdoni.io/architecture/census/off-chain.html) census is used.

> Between the three of these census methods, an incredible range of use-cases and third-party integrations for voter eligibility management is possible. Furthermore, the flexibility of the voting protocol is designed to allow more census types to be easily added in the future.

When a voting process is created, the [Census Origin](https://docs.vocdoni.io/architecture/smart-contracts/process.html#census-origin) is set to signify which type of census the process should expect to use.

### On-Chain Based Census (Ethereum ERC-20) <a href="#on-chain-based-census-ethereum-erc-20" id="on-chain-based-census-ethereum-erc-20"></a>

On-chain census allow the set of eligible voters to be expressed as a weighted census of holders of a specific token on Ethereum. There is only one entity per Ethereum token, where the address of that entity is the contract address of the given token.

To this end, [Ethereum Storage Proofs](https://docs.vocdoni.io/architecture/smart-contracts/storage-proofs.html) are used.

Anyone can permissionlessly register a token to the Storage Proof Smart Contract, incurring some gas cost. Then any holder of the token can create a voting process for that token and set the proper [census origin](https://docs.vocdoni.io/architecture/smart-contracts/process.html) value to signal the use of an on-chain census. The Census Merkle Root is the Ethereum Root Hash at a given block height, and any user can request a Merkle Proof that their address holds tokens on the target ERC20 smart contract. They can then provide this proof to vote on processes for the entity representing that token address. Weighted processes enable users to employ a voting power that is proportionate to the number of tokens they hold.

Technical details for on-chain census can be found at [On-Chain Census](https://docs.vocdoni.io/architecture/census/on-chain.html).

### Off-Chain CSP Based Census (Credential Service Provider) <a href="#off-chain-csp-based-census-credential-service-provider" id="off-chain-csp-based-census-credential-service-provider"></a>

In order to support frequent modifications to the census of an ongoing process and to bring more flexibility to the Vocdoni stack, a census based on Credential Service Providers (CSP) or Certificate Authorities (CAs) is implemented. This method allows organizations to set up a centralized authority that provides credentials to each voter, one-by-one, based on any arbitrary criteria decided by the organization.

Technical details for off-chain CSP census can be found at [Off-Chain CSP Census](https://docs.vocdoni.io/architecture/census/off-chain-csp.html).

### Off-Chain Tree Based Census (Merkle Tree) <a href="#off-chain-tree-based-census-merkle-tree" id="off-chain-tree-based-census-merkle-tree"></a>

An off-chain tree census allows organizations to centrally manage the set of members who can vote on any given process. Organizations can generate the Census Merkle Tree itself with the help of the [Census Service](https://docs.vocdoni.io/architecture/services/census-service.html), but they are responsible for manually generating a list of voters. [Vocdoni.app](https://vocdoni.app) currently provides a CSV-based census mechanism.

Technical details for off-chain tree census can be found at [Off-Chain Tree Census](https://docs.vocdoni.io/architecture/census/off-chain-tree.html).

> Details for integrating census mechanisms are documented [here](https://docs.vocdoni.io/integration/census/general.html).
