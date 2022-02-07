# Storage Proofs Contracts



The Storage Proof Contract allows token-holders to prove their balance of an ERC-20 token, thereby enabling the [On-Chain Census](https://docs.vocdoni.io/architecture/census/on-chain.html) mechanism.

## Using the Contract <a href="#using-the-contract" id="using-the-contract"></a>

The instance of the ERC20 Token Storage contract is resolved from `results.vocdoni.eth` on the ENS registry.

### Contract structs <a href="#contract-structs" id="contract-structs"></a>

```
struct ERC20Token {
    uint256 balanceMappingPosition;
    bool registered;
}

mapping(address => ERC20Token) public tokens;
address[] public tokenAddresses;
uint32 public tokenCount = 0;
```

### Methods <a href="#methods" id="methods"></a>

* `registerToken` Validates and registers the parameters of the given token contract, if not already present.

### Getters <a href="#getters" id="getters"></a>

* `isRegistered` Determines whether the given token address has been registered
* `getBalanceMappingPosition` Retrieves the offset where the balance mapping is located. Used to generate the storage proofs from the client side.
