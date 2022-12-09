<h1 align="center">⁂<br/>web3.storage</h1>
<h3 align="center">💾 w3 command line interface.</h3>
<p align="center">
  <a href="https://github.com/web3-storage/w3cli/actions/workflows/test.yaml"><img alt="GitHub Workflow Status" src="https://img.shields.io/github/workflow/status/web3-storage/w3cli/Test?style=for-the-badge" /></a>
  <a href="https://discord.com/channels/806902334369824788/864892166470893588"><img src="https://img.shields.io/badge/chat-discord?style=for-the-badge&logo=discord&label=discord&logoColor=ffffff&color=7389D8" /></a>
  <a href="https://github.com/web3-storage/w3cli/blob/main/LICENSE.md"><img alt="License: Apache-2.0 OR MIT" src="https://img.shields.io/badge/LICENSE-Apache--2.0%20OR%20MIT-yellow?style=for-the-badge" /></a>
</p>

## Getting started 

Install the CLI from npm :

```console
npm install -g @web3-storage/w3up-cli
```

Create a new space for storing your data and register it:

```console
w3 space create Documents # pick a good name!
w3 space register alice@example.com
```

Upload a file or directory:

```console
w3 up recipies.txt
```

## Commands

* Basics
  * [`w3 up`](#)
  * [`w3 ls`](#)
  * [`w3 rm`](#)
  * [`w3 open`](#)
  * [`w3 whoami`](#)
* Space management
  * [`w3 spaces add`](#)
  * [`w3 spaces create`](#)
  * [`w3 spaces ls`](#)
  * [`w3 spaces register`](#)
  * [`w3 spaces use`](#)
* Capability management
  * [`w3 delegations create`](#)
  * [`w3 delegations ls`](#)
  * [`w3 proofs add`](#)
  * [`w3 proofs ls`](#)
* Advanced usage
  * [`w3 can space info`](#)
  * [`w3 can space recover`](#)
  * [`w3 can store add`](#)
  * [`w3 can store list`](#)
  * [`w3 can store remove`](#)
  * [`w3 can upload add`](#)
  * [`w3 can upload list`](#)
  * [`w3 can upload remove`](#)

---

### `w3 up <path> [path...]`

Upload file(s) to web3.storage. The IPFS Content ID (CID) for your files is calculated on your machine, and sent up along with your files. web3.storage makes your content available on the IPFS network

- `--no-wrap` Don't wrap input files with a directory
- `-H, --hidden` Include paths that start with "."

### `w3 ls`

List all the uploads registered in the current space.

- `--json` Format as newline delimted JSON
- `--cid` Only print the root CID per upload

### `w3 rm <root-cid>`

Remove an upload from the uploads listing. Note that this command does not remove the data from the IPFS network, nor does it remove it from space storage (by default).

- `--shards` Also remove all shards referenced by the upload from the store. Use with caution and ensure other uploads do not reference the same shards.

### `w3 open <cid>`

Open a CID on https://w3s.link in your browser. You can also pass a CID and a path.

```bash
# opens a browser to https://w3s.link/ipfs/bafybeidluj5ub7okodgg5v6l4x3nytpivvcouuxgzuioa6vodg3xt2uqle
w3 open bafybeidluj5ub7okodgg5v6l4x3nytpivvcouuxgzuioa6vodg3xt2uqle

# opens a browser to https://w3s.link/ipfs/bafybeidluj5ub7okodgg5v6l4x3nytpivvcouuxgzuioa6vodg3xt2uqle/olizilla.png
w3 open bafybeidluj5ub7okodgg5v6l4x3nytpivvcouuxgzuioa6vodg3xt2uqle/olizilla.png
```

### `w3 whoami`

Print information about the current agent.

### `w3 spaces add <proof.ucan>`

Add a space to the current agent. The proof is a CAR encoded delegation to _this_ agent.

### `w3 spaces create [name]`

### `w3 spaces ls`

### `w3 spaces register <email>`

### `w3 spaces use <did>`

### `w3 delegations create <audience-did> <ability> [ability...]`

* `--name` Human readable name for the audience receiving the delegation
* `--type` Type of the audience receiving the delegation, one of: device, app, service

### `w3 delegations ls`

### `w3 proofs add <proof.ucan>`

### `w3 proofs ls`

### `w3 can space info <did>`

### `w3 can space recover <email>`

### `w3 can store add <car-path>`

Store a [CAR](https://ipld.io/specs/transport/car/carv1/) file to web3.storage.

### `w3 can store ls`

### `w3 can store rm <car-cid>`

### `w3 can upload add <root-cid> <shard-cid> [shard-cid...]`

Register an upload - a DAG with the given root data CID that is stored in the given CAR shard(s), identified by CAR CIDs.

### `w3 can upload ls`

### `w3 can upload rm <root-cid>`

## Contributing

Feel free to join in. All welcome. Please read our [contributing guidelines](https://github.com/web3-storage/w3cli/blob/main/CONTRIBUTING.md) and/or [open an issue](https://github.com/web3-storage/w3cli/issues)!

## License

Dual-licensed under [MIT + Apache 2.0](https://github.com/web3-storage/w3cli/blob/main/LICENSE.md)
