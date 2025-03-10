# radiance ☀️

Highly experimental Solana Go playground monorepo.

⚠️ **No guarantees, no support, quite possibly no documentation either.
Ignore this repo unless you're ready to read and understand the code.** ⚠️

## Available tooling

- [radiance](cmd/radiance)
  - `blockstore`: Solana validator RocksDB tool
    - `dumpshreds`: Dump raw shreds from RocksDB
    - `verifydata`: Check data integrity (parse every tx)
    - `yaml`: Dump shreds, entries, txs as YAML
  - `car`: IPLD Content Addressable Archives
    - `create`: Create replayable CAR archives from validator RocksDB
- [solrays](cmd/solrays), an RPC proxy that exports call latency of a Solana RPC node.

## Building

In order to build the available tooling, the following is required:
- Go 1.18+
- Run
  ```
  ./generate.sh
  ```

Building all the tools _should_ be as easy as:
```
:; go build -o _bin/ go.firedancer.io/radiance/cmd/...
```

All binaries will be placed in `_bin/` folder.

Or if you're just looking for a single tool, say `solrays`:
```
:; go build -o _bin/ go.firedancer.io/radiance/cmd/solrays
```

**NOTE:** Mind yourself, some of the tools here tools may depend on C code (and CGO), and other shenanigans,
so you may have to adapt accordingly.
