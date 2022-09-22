# Deploy guide

## Deploying program

Configure all program's constants for your version. You can check [_here_](structure/constants.md) in depth.

You need to confirm the Network is `devnet` (or `mainnet-beta`).

* `git clone` the repo and `cd backend` to enter the Program's source.
* Make sure you have `solana-cli` installed, keypair configured, and at least 10 sol on devnet (mainnet-beta) beforehand
* Update `Anchor.toml` config for network cluster
  * Update path to your keypair that begins with `wallet =`
  * Update cluster strings that begins with `cluster = "devnet"` or `"mainnet"`&#x20;
  * Update the program's cluster string with `program.devnet` or `program.mainnet`&#x20;
* Run `anchor build` to build the programs
* We need to update the program IDs:
  * Run `solana-keygen pubkey ./target/deploy/mutable_staking-keypair.json` - insert the new Staking prog ID in the following locations:
    * `./Anchor.toml`
    * `./programs/Mutable_Staking/src/lib.rs`
    * `./cli/script.ts`
* Run `anchor build` to build one more time
* Run `anchor deploy --provider.cluster devnet` to deploy to devnet (or `mainnet-beta` for mainnet)
* Now copy the IDLs into the apps:
  * `cp ./target/idl/mutable_staking.json ./cli/mutable_staking.json`&#x20;
* (!) IMPORTANT - update the wallet keypair path in `package.json` with `ts-node` script; in `export ANCHOR_WALLET=`&#x20;
* run `yarn ts-node` inside the root of the program source to use the program's `cli` script commands for admin maintain

{% hint style="info" %}
Note that deploying your own version will cost you 5\~6 SOL.
{% endhint %}

