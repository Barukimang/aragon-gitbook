# Entity Resolver Contract

Voters may want to access an index of the available elections. The best way to organize them is by grouping them by the entity that created them.

In Vocdoni, entities publish [human readable metadata](https://docs.vocdoni.io/architecture/data-schemes/entity-metadata), but such metadata needs to be securely indexed on a Smart Contract.

The ENS Resolver Smart Contract allows entities to register and set the [Content URI](https://docs.vocdoni.io/architecture/protocol/data-origins.html#content-uri) that points to the actual [JSON metadata](https://docs.vocdoni.io/architecture/data-schemes/entity-metadata).

### Entity Resolver <a href="#entity-resolver" id="entity-resolver"></a>

The **Entity Resolver** is the smart contract where [the metadata of each entity](https://docs.vocdoni.io/architecture/data-schemes/entity-metadata) is indexed. It leverages a standard ENS Resolver contract for its Text records, used as a key-value store.

The instance of the Results contract is resolved from `entities.vocdoni.eth` on the ENS registry. In the case of Ethereum chains like `xdai` or `sokol`, the contract can also act as a global ENS resolver.

The `entityId` is the unique identifier of each entity, being a hash of its Ethereum address:

```json
bytes32 entityId = keccak256 (entityAddress);
```

### Text Record storage <a href="#text-record-storage" id="text-record-storage"></a>

We make use of [EIP 634: Storage of Text records in ENS](https://eips.ethereum.org/EIPS/eip-634). It is a convenient way to store arbitrary data as a string following a key-value store model.

[Implementation](https://github.com/vocdoni/dvote-solidity/blob/master/contracts/profiles/TextResolver.sol)

### Supported Text Record keys <a href="#supported-text-record-keys" id="supported-text-record-keys"></a>

Entities may define the following Text Records:

| Key                             | Example                                                       | Description                                                                                                                                                                                                                                                                                         |
| ------------------------------- | ------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `vnd.vocdoni.meta`              | 'ipfs://12345,https://server/json'                            | <p><a href="https://docs.vocdoni.io/architecture/protocol/data-origins.html#content-uri">Content URI</a> to fetch the Entity's JSON metadata.<br>See <a href="https://docs.vocdoni.io/architecture/smart-contracts/entity-resolver.html#meta">JSON schema</a>.</p>                                  |
| `vnd.vocdoni.boot-nodes`        | 'ipfs://12345,https://server/gw.json'                         | <p><a href="https://docs.vocdoni.io/architecture/protocol/data-origins.html#content-uri">Content URI</a> to fetch a set of Gateways for the Entity.<br>See <a href="https://docs.vocdoni.io/architecture/smart-contracts/entity-resolver.html#gateway-boot-nodes">Gateway Boot Nodes</a> below.</p> |
| `vnd.vocdoni.gateway-heartbeat` | 'wss://host/path'                                             | [Messaging URI](https://docs.vocdoni.io/architecture/protocol/data-origins.html#messaging-uri) where the Gateways of the entity should report their health status.                                                                                                                                  |
| `vnd.vocdoni.archive`           | 'ipns://12345,QmSrPmbaUKA3ZodhzPWZnpFgcPMFWF4QsxXbkWfEptTBJd' | [Content URI](https://docs.vocdoni.io/architecture/protocol/data-origins.html#content-uri) to fetch the process archive record.                                                                                                                                                                     |

* Required
  * `vnd.vocdoni.meta`
* Optional
  * `vnd.vocdoni.boot-nodes`
  * `vnd.vocdoni.gateway-heartbeat` (as long as the entity has no Gateways)
  * `vnd.vocdoni.archive`

**JSON Metadata**

See [Entity Metadata](https://docs.vocdoni.io/architecture/data-schemes/entity-metadata.html#json-schema).

**Gateway boot nodes**

Client apps may not be able to join P2P networks by themselves, so Vocdoni makes use of [Gateways](https://docs.vocdoni.io/architecture/services/gateway) to enable decentralized transactions over HTTP or Web Sockets. A gateway Boot Node is a service provided by the Entity, and it defines a list of active Gateways that a client can use.

By default, Vocdoni (as an Entity) provides its own set of Voting and Web3 Gateways. However, entities may want to use their own infrastructure. To this end, the Entity's ENS Text Record `vnd.vocdoni.boot-nodes` can be set to the Content URI of a [BootNodes JSON file](https://docs.vocdoni.io/architecture/services/bootnode) defining some of them.
