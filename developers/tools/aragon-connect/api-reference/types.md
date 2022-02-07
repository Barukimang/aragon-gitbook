# Types

This page describes the data types shared that are shared between the different Connect packages.

## `Networkish` <a href="#networkish" id="networkish"></a>

Networkish can be a number, a string or an object.

### As a number

### As a number

| Type     | Description                                       |
| -------- | ------------------------------------------------- |
| `number` | [Chain ID](https://chainid.network) of a network. |

| Type     | Description                                       |
| -------- | ------------------------------------------------- |
| `number` | [Chain ID](https://chainid.network) of a network. |

### As a string

### As a string

| Type         | Description |
| ------------ | ----------- |
| \`"ethereum" | "rinkeby"   |

| Type         | Description |
| ------------ | ----------- |
| \`"ethereum" | "rinkeby"   |

### As an object

### As an object

| Name         | Type     | Description                                                                                                               |
| ------------ | -------- | ------------------------------------------------------------------------------------------------------------------------- |
| `chainId`    | `number` | [Chain ID](https://chainid.network) of a network.                                                                         |
| `ensAddress` | `string` | Address of the ENS resolver (optional). If not provided, Connect will attempt to find one that correspond to the chainID. |
| `name`       | `string` | Name of the network. It will be passed to ethers.js internally.                                                           |

| Name         | Type     | Description                                                                                                               |
| ------------ | -------- | ------------------------------------------------------------------------------------------------------------------------- |
| `chainId`    | `number` | [Chain ID](https://chainid.network) of a network.                                                                         |
| `ensAddress` | `string` | Address of the ENS resolver (optional). If not provided, Connect will attempt to find one that correspond to the chainID. |
| `name`       | `string` | Name of the network. It will be passed to ethers.js internally.                                                           |

## `IpfsResolverDeclaration`

## `IpfsResolverDeclaration`

IpfsResolverDeclaration can be a string, an object, or a `IpfsResolver` instance.

IpfsResolverDeclaration can be a string, an object, or a `IpfsResolver` instance.

### As a string

### As a string

| Type     | Description                                                                                                 |
| -------- | ----------------------------------------------------------------------------------------------------------- |
| `string` | [URL template](https://en.wikipedia.org/wiki/URI\_Template) containing the `{cid}` and `{path}` parameters. |

| Type     | Description                                                                                                 |
| -------- | ----------------------------------------------------------------------------------------------------------- |
| `string` | [URL template](https://en.wikipedia.org/wiki/URI\_Template) containing the `{cid}` and `{path}` parameters. |

### As an object

### As an object

| Name          | Type     | Description                                                                                                            |
| ------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| `urlTemplate` | `string` | [URL template](https://en.wikipedia.org/wiki/URI\_Template) containing the `{cid}` and `{path}` parameters (optional). |
| `cache`       | `number` | The number of query results to cache. Set to `0` to disable the cache (optional).                                      |

| Name          | Type     | Description                                                                                                            |
| ------------- | -------- | ---------------------------------------------------------------------------------------------------------------------- |
| `urlTemplate` | `string` | [URL template](https://en.wikipedia.org/wiki/URI\_Template) containing the `{cid}` and `{path}` parameters (optional). |
| `cache`       | `number` | The number of query results to cache. Set to `0` to disable the cache (optional).                                      |

