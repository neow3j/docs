﻿# getwalletunclaimedgas Method

Gets the amount of unclaimed GAS in the wallet.

> [!Note]
>
> Before you can invoke this method you must:
>
> 1. Install the plugin [RpcServer](https://github.com/neo-project/neo-plugins/releases)
> 2. Call the RPC method `openwallet` to open the wallet first.

## Example

Request body:

```json
{
  "jsonrpc": "2.0",
  "method": "getwalletunclaimedgas",
  "params": [],
  "id": 1
}
```

Response body:

```json
{
  "jsonrpc": "2.0",
  "id": 1,
  "result": "897299680935"
}
```

Response description:

Returns the unclaimed GAS amount.
