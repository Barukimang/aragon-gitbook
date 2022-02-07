# Govern.js API

**Usage with default config**

> The default config uses the Govern servers deployed by Aragon

```javascript
import { dao } from '@aragon/govern'

const response = await dao('0x0...')

console.log(response)
```

**Usage with custom config**

```javascript
import { dao, configure } from '@aragon/govern'

configure({ governURL: 'https://myOwnGovernServer.io' })

const response = await dao('0x0...')

console.log(response)
```

### dao(name) ⇒ `Promise<Dao>`

Returns details about a DAO by his address.

| Param | Type     | Description         |
| ----- | -------- | ------------------- |
| name  | `string` | The name of the DAO |

Example:

```typescript
import { dao } from '@aragon/govern'

const response = await dao('0x0...')
```

### daos() ⇒ `Promise<Dao[]>`

Returns all DAOs.

Example:

```typescript
import { daos } from '@aragon/govern'

const response = await daos()
```

### query(query, args) ⇒ `Promise<object>`

Returns the desired data.

| Param | Type     | Description            |
| ----- | -------- | ---------------------- |
| query | `string` | GraphQL query          |
| args  | `object` | Object with parameters |

Example:

```typescript
import { query } from '@aragon/govern'

const query = await query(myQuery, {...});
```

### createDao(args, options) ⇒ `Promise<TransactionResponse>`

Create

| Param   | Type               | Description                            |
| ------- | ------------------ | -------------------------------------- |
| args    | `CreateDaoParams`  | Dao name, Dao token, useProxies option |
| options | `CreateDaoOptions` | EIP 1193 provider, Dao factory address |

Examples:

For Node.js:

```typescript
import { createDao } from '@aragon/govern'

const result = await createDao(args, options)
```

### configure(config) ⇒ `void`

Overwrites the default configuration of govern.

| Param  | Type                                                                                                                             | Description                                                                                                                               |
| ------ | -------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| config | [`ConfigurationObject`](https://github.com/aragon/govern/tree/master/packages/govern/internal/configuration/Configuration.ts#L4) | Object with all [config options](https://github.com/aragon/govern/tree/master/packages/govern/internal/configuration/Configuration.ts#L4) |

Example:

```typescript
import { configure } from '@aragon/govern'

configure({ governURL: 'https://myOwnGovernServer.io' })
```

### &#x20;<a href="#dao-name-promise-less-than-dao-greater-than" id="dao-name-promise-less-than-dao-greater-than"></a>

