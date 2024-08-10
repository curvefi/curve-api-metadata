## curve-api-metadata

This repository serves as a metadata store for [Curve API](https://github.com/curvefi/curve-api) config files open to community contributions.

## Files

### `ethereum-lst-defillama.json`

List of ETH LST metadata that match single entries returned from https://yields.llama.fi/pools (an open API provided by [Defillama](https://defillama.com/docs/api)), used by the Curve API to retrieve native staked ETH APYs for staked ETH tokens used in any number of Curve pools

**How to add a new entry:**

- Create a new object in the JSON file that describes the entry.
- `defillamaProps` are the two properties that the system will use to find the new entry's yield data inside [https://yields.llama.fi/pools](https://yields.llama.fi/pools): `project` and `symbol` must match the relevant item in that endpoint.
- `lstAddresses` identify the relevant token addresses for this yield data.

Example: Lido’s wstETH yield data can be found inside [https://yields.llama.fi/pools](https://yields.llama.fi/pools) with properties `project = "lido"` and `symbol = "STETH"`, and its token address on Ethereum mainnet is `"0x7f39c581f595b53c5cb19bd0b3f8da6c935e2ca0"`, so its JSON description is:

```json
{
    "defillamaProps": {
        "project": "lido",
        "symbol": "STETH"
    },
    "lstAddresses": [{
        "address": "0x7f39c581f595b53c5cb19bd0b3f8da6c935e2ca0",
        "blockchainId": "ethereum"
    }]
}
```
