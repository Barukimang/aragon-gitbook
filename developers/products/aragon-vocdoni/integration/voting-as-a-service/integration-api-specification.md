# Integration API Specification

The service exposes an HTTP Restful API with the following endpoints.

### Internal API <a href="#internal-api" id="internal-api"></a>

The group of calls below is intended for the admin running the service itself.

**Superadmin related**

#### Create an integrator account <a href="#create-an-integrator-account" id="create-an-integrator-account"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <superadmin-key>" https://server/v1/admin/accounts
```

**Request body**

```json
{
	"cspUrlPrefix": "my-csp-url-prefix",
	"cspPubKey": "hexBytes",
	"name": "My integrator account",
    "email": "admin@account.net"
}
```

**HTTP 200**

```json
{
	"id": "1234567890",
	"apiKey": "ksjdhfksjdh..."   // The integrator (secret) key to use the API
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Update an integrator account <a href="#update-an-integrator-account" id="update-an-integrator-account"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X PUT -H "Authorization: Bearer <superadmin-key>" https://server/v1/admin/accounts/<id>
```

**Request body**

```json
{
	"cspUrlPrefix": "my-csp-url-prefix",
	"cspPubKey": "hexBytes",
	"name": "My integrator account",
}
```

**HTTP 200**

```json
{
    "id": "1234567890"
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Reset an integrator API key <a href="#reset-an-integrator-api-key" id="reset-an-integrator-api-key"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X PATCH -H "Authorization: Bearer <superadmin-key>" https://server/v1/admin/accounts/<id>/key
```

**HTTP 200**

```json
{
    "id": "1234567890",
    "apiKey": "priv_abcdefghijklmnoprstuvwxyz"
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```



</details>

#### Get an integrator account

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <superadmin-key>" https://server/v1/admin/accounts/<id>
```

**HTTP 200**

```json
{
	"cspUrlPrefix": "my-csp-url-prefix",
	"cspPubKey": "hexBytes",
	"name": "My integrator account",
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Delete an integrator account <a href="#delete-an-integrator-account" id="delete-an-integrator-account"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X DELETE -H "Authorization: Bearer <superadmin-key>" https://server/v1/admin/accounts/<id>
```

**HTTP 200**

```
// empty response
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

### Integrator API (Private) <a href="#integrator-api-private" id="integrator-api-private"></a>

**Integrator related**

The following endpoints are authenticated by using the integrator secret key. They allow integrators to manage the organizations related to their customers.

#### Create an organization <a href="#create-an-organization" id="create-an-organization"></a>

<details>

<summary>Example</summary>

This request submits a transaction to the \[voting blockchain]\(../architecture/services/vochain.md) which can take some time (\~15 seconds) to be accepted and mined. Therefore, the return values of this method should not be considered valid until the Transaction Status method is called, using the \`txHash\` value to confirm that the desired transaction has been mined. Only then is it safe to query for the organization you have created.

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/account/organizations
```

**Request body**

```json
{
    "name": "Organization name",
    "description": "my-description",
    "header": "https://my/header.jpeg",
    "avatar": "https://my/avatar.png"
}
```

**HTTP 200**

```json
{
    "organizationId": "0x1234...",
    "apiToken": "pub_qwertyui...",   // API token for public voting endpoints
    "txHash": "0x1234...",
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Get an organization <a href="#get-an-organization" id="get-an-organization"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/account/organizations/<organizationId>
```

**HTTP 200**

```json
{
    "apiToken": "qoiuwhgoiauhsdaiouh",   // the public API token
    "name": "Organization name",
    "description": "",
    "header": "https://my/header.jpeg",
    "avatar": "https://my/avatar.png"
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Remove an organization <a href="#remove-an-organization" id="remove-an-organization"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X DELETE -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/account/organizations/<organizationId>
```

**HTTP 200**

```
// empty response
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Reset the public API token of an organization <a href="#reset-the-public-api-token-of-an-organization" id="reset-the-public-api-token-of-an-organization"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X PATCH -H "Authorization: Bearer <integrator-key>" https://server/v1/account/organizations/<id>/key
```

**HTTP 200**

```json
{
    "apiToken": "zxcvbnm"
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

**Organization related**

These methods are also intended for integrators, but they are expected to do the duties of an organization managing a proposal.

#### Set Organization metadata <a href="#set-organization-metadata" id="set-organization-metadata"></a>

<details>

<summary>Example</summary>

This request submits a transaction to the \[voting blockchain]\(../architecture/services/vochain.md) which can take some time (\~15 seconds) to be accepted and mined. Therefore, the return values of this method should not be considered valid until the Transaction Status method is called, using the \`txHash\` value to confirm that the desired transaction has been mined. Only then is it safe to query for the organization you have updated.

**Request**

```
curl -X PUT -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/metadata
```

**Request body**

```json
{
    "name": "Organization name",
    "description": "my-description",
    "header": "https://my/header.jpeg",
    "avatar": "https://my/avatar.png"
}
```

**HTTP 200**

```json
{
    "organizationId": "0x1234...",
    "contentUri": "ipfs://1234...",
    "txHash": "0x1234...",
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Check a transaction status <a href="#check-a-transaction-status" id="check-a-transaction-status"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -X GET -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/transactions/<transaction-hash>
```

**HTTP 200**

```json
{
    "mined": true // true | false
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Create an election <a href="#create-an-election" id="create-an-election"></a>

Generates a Merkle Tree with the given current census keys and generates a voting process with the given metadata.

<details>

<summary>Example</summary>

This request submits a transaction to the voting blockchain which can take some time (\~15 seconds) to be accepted and mined. Therefore, the return values of this method should not be considered valid until the Transaction Status method is called, using the `txHash` value to confirm that the desired transaction has been mined. Only then is it safe to query for the election you have created.

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/signed
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/blind
```

**Request body**

```json
{
    "title": "Important election",
    "description": "Description here",
    "header": "https://my/header.jpeg",
    "streamUri": "https://youtu.be/1234",
    "startDate": "2021-10-25T11:20:53.769Z", // can be empty
    "endDate": "2021-10-30T12:00:00.000Z",
    "questions": [
        {
            "title": "Question 1",
            "description": "(optional)",
            "choices": ["Yes", "No", "Maybe"]  // simplified version of title/value
        }, {...}
    ],
    "confidential": false,  // Metadata access restricted to only census members
    "hiddenResults": true, // Encrypt results until the election ends
    "census": "<censusId>" // Optional for CSP processes
}
```

**HTTP 200**

```json
{
    "electionId": "0x1234...",
    "txHash": "0x1234...",
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Set an election status <a href="#set-an-election-status" id="set-an-election-status"></a>

Generates a Merkle Tree with the given current census keys and generates a voting process with the given metadata.

<details>

<summary>Example</summary>

This request submits a transaction to the voting blockchain which can take some time (\~15 seconds) to be accepted and mined. Therefore, the desired results of this method should not be considered valid until the Transaction Status method is called, using the `txHash` value to confirm that the desired transaction has been mined. Only then is it safe to query for the election you have updated.

**Request**

```
curl -X PUT -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/elections/<electionId>/status
```

**Request body**

```json
{
    "status": "READY" // READY, ENDED, CANCELED, PAUSED
}
```

**HTTP 200**

```json
{
    "txHash": "0x1234..."
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### List elections (filtered) <a href="#list-elections-filtered" id="list-elections-filtered"></a>

Allows unrestricted listing, paging and filtering for the integrator backend to display all info to organization admins.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections

curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/upcoming
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/active
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/paused
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/canceled
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/ended

curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/blind
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/organizations/<organizationId>/elections/signed
```

**HTTP 200**

```json
[
    {
        "title": "Important election",
        "description": "",
        "header": "https://my/header.jpeg",
        "status": "UPCOMING", // "UNKNOWN" | "PAUSED" | "CANCELED" | "UPCOMING" | "ACTIVE" | "ENDED"
        "startDate": "2021-10-25T11:20:53.769Z", // can be empty
        "endDate": "2021-10-30T12:00:00.000Z",
        "proofType": "blind", // "blind | "ecdsa"
    }, {...}
]
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Get an election <a href="#get-an-election" id="get-an-election"></a>

Allows unrestricted access for the integrator backend to display all info to organization admins. Confidential elections do not require any additional step, just the integrator API key.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/elections/<electionId>
```

**Request body**

```json
{
  "type": "blind-confidential-hidden-results",
  "organizationId": "20323909c3e0965d1489893db1512b32b55707ea",
  "title": "test election",
  "description": "description test 1",
  "header": "https://source.unsplash.com/random/800x600",
  "questions": [
    {
      "title": "test q1",
      "description": "",
      "choices": [
        "Yes",
        "No"
      ]
    },
    {
      "title": "test q2",
      "description": "",
      "choices": [
        "Yes",
        "No"
      ]
    },
    {
      "title": "test q3",
      "description": "",
      "choices": [
        "Yes",
        "No"
      ]
    }
  ],
  "status": "ENDED", // "UNKNOWN" | "PAUSED" | "CANCELED" | "UPCOMING" | "ACTIVE" | "ENDED"
  "proofType": "blind", // "blind" | "ecdsa"
  "streamUri": "uri",
  "voteCount": 1,
  "results": [
    {
      "title": [
        "Yes",
        "No"
      ],
      "value": [
        "1",
        "0"
      ]
    },
    {
      "title": [
        "Yes",
        "No"
      ],
      "value": [
        "1",
        "0"
      ]
    },
    {
      "title": [
        "Yes",
        "No"
      ],
      "value": [
        "1",
        "0"
      ]
    }
  ],
  "organizationId": "20323909c3e0965d1489893db1512b32b55707ea",
  "electionId": "47f2c1f1164a27db4f5e7b825f8ec064c44da88a83ff72b90e5755fff8bfb53b",
  "aggregation": "discrete-counting",
  "display": "multiple-question"
}
```

**HTTP 200**

```json
{
    "electionId": "0x1234..."
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Create a census <a href="#create-a-census" id="create-a-census"></a>

A census where public keys or token slots (that will eventually contain a public key) are stored. A census can start with 0 items, and public keys can be imported later on.

If census tokens are allocated, users will need to generate a wallet on the frontend and register the public key by themselves. This prevents both the API and the integrator from gaining access to the private key.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses
```

**Request body**

```json
{
    "name": "2021 members"
}
```

**HTTP 200**

```json
{
    "censusId": "123456789..."
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Add N census tokens (once) <a href="#add-n-census-tokens-once" id="add-n-census-tokens-once"></a>

Creates N census tokens for voters to register their public key in the future.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/tokens/flat
```

**Request body**

```json
{
    "size": 450
}
```

**HTTP 200**

```json
{
    "censusId": "123456789...",
    "size": 700,  // new size
    "tokens": [
        "jashdlkfjahs", "uyroeituwyert", "e7rg9e87rn9", ... // x 450
    ]
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Add weighted census tokens (once) <a href="#add-weighted-census-tokens-once" id="add-weighted-census-tokens-once"></a>

Creates weighted census tokens so that voters with the token can register their public key to the appropriate census weight.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/tokens/flat
```

**Request body**

```json
{
    "size": 450
}
```

**HTTP 200**

```json
{
    "censusId": "123456789...",
    "size": 700,  // new size
    "tokens": [
        "jashdlkfjahs", "uyroeituwyert", "e7rg9e87rn9", ... // x 450
    ]
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Get census token (see a registered public key) <a href="#get-census-token-see-a-registered-public-key" id="get-census-token-see-a-registered-public-key"></a>

Allows integrators to check the status of a census token, given to a user.

If the token has already been redeemed, the public key will be used as part of the census normally.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/tokens/<tokenId>
```

**HTTP 200**

```json
{
    "publicKey": "",   // no public key yet
    "weight": 20
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Remove a census token or public key from a census <a href="#remove-a-census-token-or-public-key-from-a-census" id="remove-a-census-token-or-public-key-from-a-census"></a>

Removes the given token or key from the given census. The next time it is used, the new key will be in effect.

<details>

<summary>Example</summary>

**Request**

```
curl -X DELETE -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/tokens/<tokenId>
curl -X DELETE -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/keys/<publicKey>
```

**HTTP 200**

```json
// empty response
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Import public keys into a census <a href="#import-public-keys-into-a-census" id="import-public-keys-into-a-census"></a>

Import a group of public keys to an existing census. All voters have the same weight (1).

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/import/flat
```

**Request body**

```json
{
    "publicKeys": [
        "0x0312345678...",
        "0x0223456789...",
        ...
    ]
}
```

**HTTP 200**

```json
{
    "censusId": "123456789...",
    "size": 300
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

#### Import weighted public keys into a census <a href="#import-weighted-public-keys-into-a-census" id="import-weighted-public-keys-into-a-census"></a>

Import a group of public keys to an existing census, using their respective weight.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <integrator-key>" https://server/v1/priv/censuses/<censusId>/import/weighted
```

**Request body**

```json
{
    "entries": [
        { "publicKey": "0x0312345678...", "weight": 100 },
        { "publicKey": "0x02234567890...", "weight": 150 },
        ...
    ]
}
```

**HTTP 200**

```json
{
    "censusId": "123456789...",
    "size": 300
}
```

**HTTP 400**

```json
{
    "error": "Message goes here"
}
```

</details>

### Public API <a href="#public-api" id="public-api"></a>

(token API authenticated, voter apps call it directly)

#### Get election list (per organization) – non-confidential <a href="#get-election-list-per-organization-non-confidential" id="get-election-list-per-organization-non-confidential"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections

curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/upcoming
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/active
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/paused
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/canceled
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/ended

curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/blind
curl -H "Authorization: Bearer <manager-key>" https://server/v1/pub/organizations/<organizationId>/elections/signed
```

**HTTP 200**

```
[
    {
        "id": "0x12345678...",
        "title": "Important election",
        "avatar": "https://my/avatar.png",
        "startDate": "2021-12-25T11:20:53.769Z",
        "endDate": "2021-10-30T12:00:00.000Z",
        "confidential": false,
        "hiddenResults": true,
        "proofType": "blind", // "blind | "ecdsa"
    }, {...}
]
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Get election info – non-confidential <a href="#get-election-info-non-confidential" id="get-election-info-non-confidential"></a>

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/elections/<electionId>
```

**HTTP 200**

```
{
    "type": "signed-plain", // blind-plain, ...
    "title": "Important election",
    "description": "Description goes here",
    "header": "https://my/header.jpeg",
    "streamUri": "https://youtu.be/1234",
    "questions": [
        {
            "title": "Question 1",
            "description": "(optional)",
            "choices": ["Yes", "No", "Maybe"]
        }, {...}
    ],
    "status": "UPCOMING", // "UNKNOWN" | "PAUSED" | "CANCELED" | "UPCOMING" | "ACTIVE" | "ENDED"
    "voteCount": 1234,
    "proofType": "blind", // "blind" | "ecdsa"
    "results": [   // Empty array when no results []
        [ { "title": "Yes", "value": "1234" }, { "title": "No", "value": "2345" } ],
        [ { "title": "Yes", "value": "22" }, { "title": "No", "value": "33" } ]
    ]
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Get election info – confidential <a href="#get-election-info-confidential" id="get-election-info-confidential"></a>

Provides the details of a confidential voting process if the user holds a wallet that belongs to its census.

If `{electionId}` has been signed by the CSP, then it gets the Vochain parameters, decrypts the metadata and returns it to the caller.

URL Params:

* election-id
* signed-pid: `sign({electionId}, voterPrivK)`
* csp-signature: `sign({electionId}, cspPrivK)`
  * [See here](https://www.notion.so/Vocdoni-API-v1-86357bf911a24e33ab7159a2b6e54632)

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/elections/<election-id>/auth/<csp-shared-key>
```

**HTTP 200**

```
{
    "type": "signed-plain", // blind-plain, ...
    "title": "Important election",
    "description": "Description goes here",
    "header": "https://my/header.jpeg",
    "streamUri": "https://youtu.be/1234",
    "questions": [
        {
            "title": "Question 1",
            "description": "(optional)",
            "choices": ["Yes", "No", "Maybe"]
        }, {...}
    ],
    "status": "UPCOMING", // "UNKNOWN" | "PAUSED" | "CANCELED" | "UPCOMING" | "ACTIVE" | "ENDED"
    "proofType": "blind", // "blind" | "ecdsa"
    "voteCount": 1234,
    "results": [   // Empty array when no results []
        [ { "title": "Yes", "value": "1234" }, { "title": "No", "value": "2345" } ],
        [ { "title": "Yes", "value": "22" }, { "title": "No", "value": "33" } ]
    ]
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Requesting a census proof <a href="#requesting-a-census-proof" id="requesting-a-census-proof"></a>

People voting on a signed process will need to package a vote envelope using the result of this call.

Note: This call does not apply to deployments where a custom CSP validation is being used.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/elections/<electionId>/proof
```

**Request body**

```
{
    "signature": "0x12345678..." // signing a well-known payload using the wallet
}
```

**HTTP 200**

```
{
    "proof": "..."
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Submitting a vote (signed or blind) <a href="#submitting-a-vote-signed-or-blind" id="submitting-a-vote-signed-or-blind"></a>

Voters using the tiny JS SDK will get a base64 bundle including the vote and the census proof. This payload is submitted as a base64 string.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/elections/<electionId>/vote
```

**Request body**

```
{
    "vote": "<base64-signed-vote-transaction>" // see dvote-js
}
```

**HTTP 200**

```
{
    "nullifier": "0x12345678..."
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Getting a ballot (nullifier) <a href="#getting-a-ballot-nullifier" id="getting-a-ballot-nullifier"></a>

Voters can check the status of their vote here, and eventually check the explorer link, for independent confirmation.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/nullifiers/<nullifier>
```

**HTTP 200**

```
{
    "electionId": "0x12345678...",
    "registered": true,
    "explorerUrl": "https://vaas.explorer.vote/nullifiers/0x12345678"
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Registering a voter's public key <a href="#registering-a-voter-s-public-key" id="registering-a-voter-s-public-key"></a>

This process needs to be done by the integrator's frontend, once.

As soon as a user runs an updated UI version, a new private key should be generated, and the public key should be registered, so that new votes can use this key.

If the wallet is lost, the integrator will need to remove the pubKey from the census and create a new census token when the new wallet is available.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/censuses/<censusId>/token
```

**Request body**

```
{
    "censusToken": "jashdlkfjahs",
    "publicKey": "0x03abcdef0123456789..."
}
```

**HTTP 200**

```
// empty response
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

### Authentication API <a href="#authentication-api" id="authentication-api"></a>

**Generic authentication**

#### Get a shared key to access the private data of an election <a href="#get-a-shared-key-to-access-the-private-data-of-an-election" id="get-a-shared-key-to-access-the-private-data-of-an-election"></a>

The CSP issues a per-process signature whenever the wallet belongs to the process's census. The signature can be used to retrieve confidential information, restricted to only census members.

The voter signs the `electionID` to prove that he/she has a private key within the election census. If everything is correct, the CSP returns `sign({electionId}, cspPrivK)`.

* election-id
* signed-pid: `sign({electionId}, voterPrivK)`

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<election-id>/sharedkey
```

**Request body**

```
{
	"authData": ["<signed-pid>"]
}
```

**HTTP 200**

```
{
    "sharedkey": "0x1234567890abcde..."
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Get a token for requesting a plain/blind signature <a href="#get-a-token-for-requesting-a-plain-blind-signature" id="get-a-token-for-requesting-a-plain-blind-signature"></a>

The blind signature process involves a two step interaction.

In the first interaction, the voter proves to have a private key within the election census. If everything is correct, the backend replies with the `tokenR`, which the voter needs to use on the second step.

* process-id
* signed-pid: `sign({electionId}, voterPrivK)`

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<election-id>/ecdsa/auth
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<election-id>/blind/auth
```

**Request body**

```
{
	"authData": ["<signed-pid>"]
}
```

**HTTP 200**

```
{
    "tokenR": "0x1234567890abcde..."
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Request the plain/blind signature for an ephemeral wallet <a href="#request-the-plain-blind-signature-for-an-ephemeral-wallet" id="request-the-plain-blind-signature-for-an-ephemeral-wallet"></a>

The user generates an ephemeral wallet and the received tokenR to generate a (plain or blinded) payload. This payload is sent to the backend, which will check the correctness and reply with a signature of the payload.

The voter then may unblind the response (if applicable) and use it as their vote signature.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<electionId>/ecdsa/sign
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<electionId>/blind/sign
```

**Request body**

```
{
    "payload": "0xabcdef...",   // hash({electionId, address}) or blind(hash({electionId, address}))
    "tokenR": "0x1234567890abcde..."
}
```

**HTTP 200**

```
{
    "signature": "0x1234567890abcde..."  // plain or blind signature
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Get the public keys that have requested a blind signature on an election <a href="#get-the-public-keys-that-have-requested-a-blind-signature-on-an-election" id="get-the-public-keys-that-have-requested-a-blind-signature-on-an-election"></a>

For transparency, external observers can request the exhaustive list of public keys that made a blind signature request.

<details>

<summary>Example</summary>

**Request**

```
curl -H "Authorization: Bearer <organization-api-token>" https://server/v1/pub/elections/<electionId>/blind/authorized
```

**HTTP 200**

```
{
    "publicKeys": [
        "0x12345678...",
        "0x23456789...",
        ...
    ]
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

**Custom authentication API**

#### Get a shared key to access the private data of an election <a href="#get-a-shared-key-to-access-the-private-data-of-an-election-2" id="get-a-shared-key-to-access-the-private-data-of-an-election-2"></a>

This endpoint is conceptually the same as the one from above. The only difference lies on the custom logic that decides whether a voter is eligible or not.

The CSP issues a per-process signature whenever the wallet belongs to the process's census. The signature can be used to retrieve confidential information, restricted to only census members.

If the evidence provided is correct, the CSP returns `sign({electionId}, cspPrivK)`.

* election-id
* signed-pid: `sign({electionId}, voterPrivK)`

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/elections/<election-id>/sharedkey
```

**Request body**

````
{
    "authData": ["param1", "param2", ...]
}
#### HTTP 200
```json
{
    "sharedkey": "0x1234567890abcde..."
}
````

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>

#### Get a token for requesting a blind signature - custom <a href="#get-a-token-for-requesting-a-blind-signature-custom" id="get-a-token-for-requesting-a-blind-signature-custom"></a>

This endpoint is conceptually the same as the one from above. The only difference lies on the custom logic that decides whether a `tokenR` is generated or not.

The blind signature process involves a two step interaction.

In the first interaction, the voter proves their eligibility. If everything is correct, the backend replies with the `tokenR`, which the voter needs to use on the second step.

<details>

<summary>Example</summary>

**Request**

```
curl -X POST -H "Authorization: Bearer <organization-api-token>" https://server/v1/auth/custom/elections/<electionId>/blind/auth
```

**Request body**

```
{
    "authData": ["param1", "param2", ...]
}
```

**HTTP 200**

```
{
    "tokenR": "0x1234567890abcde..."
}
```

**HTTP 400**

```
{
    "error": "Message goes here"
}
```

</details>
