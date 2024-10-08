# rust-simple_blockchain

- Simple example for building a blockchain in Rust.
- Forked by Kyle Romero from https://github.com/zupzup/rust-blockchain-example.
- No new code has currently been written; I am using this project to understand Rust, Rust Runner IDE, and Blockchain concepts.
- Note: I built this on Windows 10, and had to add an environment variable for RUST_LOG=info for the console display to work correctly. I could then start with cargo run.

Start using

```bash
RUST_LOG=info cargo run
```

This starts the client locally. The blockchain is not persisted anywhere.

You can start it in multiple terminals to get multiple connected peer-to-peer clients.

In each client, you can enter the following commands:

* `ls p` - list peers
* `ls c` - print local chain
* `create b $data` - `$data` is just a string here - this creates (mines) a new block with the data entry `$data` and broadcasts it

Once a block is created by a node, it's broadcasted and the blockchain in all other nodes is updated (if it's a valid block).

On startup, a node asks another node on the network for their blockchain and, if it's valid and longer than the current local blockchain, it updates it's own chain to the longest one it receives.


This is a VERY overly simplified, offline-running, highly inefficient and insecure blockchain implementation. If a node gets out of sync, it's broken. This is an example for showing some of the concepts behind building a blockchain system in Rust, so it shouldn't be used anywhere near a production scenario, but you can have fun with it and learn something. :)
