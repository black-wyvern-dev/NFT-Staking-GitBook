# Configure guide

Before launch your staking website, you should configure all values according to your deployed programs configurations.

You can check all configure values in `./frontend/src/config.tsx` file.



`EPOCH` - reward generated time by second. This is used to calculate current available reward.

`USER_POOL_SIZE` - program's User PDA account size. This is used to create and rent the User PDA of Staking program. Calculated as following. You can check the User PDA structure [_here_](../on-chain-program/structure/data-layout.md#minimum-version-requirements-1)_._

&#x20;      `8 + 32 + 8 + 8 + 8 + (32 + 8) * STAKE_MAX_COUNT`

`REWARD_TOKEN_MINT` - reward token mint pubkey.

`PROGRAM_ID` - deployed staking program's id.

`REWARD_TOKEN_DECIMAL` - reward token decimal value.

`COLLECTION_CREATOR` - NFT collection's creator address to filter a particular NFT collection.

`PUBLISH_NETWORK` - _"devnet"_ for devnet, _"mainnet"_ for mainnet. This is used to link the transaction signatures to **solscan** or **explorer** in the transaction notifications.

{% hint style="info" %}
Note that you should confirm the network connection cluster in this code.

_export const solConnection = new web3.Connection(web3.clusterApiUrl("devnet"));_

Cluster string for devnet is _'devnet'_ and _'mainnet-beta'_ for mainnet.
{% endhint %}

