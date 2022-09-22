---
description: Description for maintaining the Staking Program as its owner.
---

# Command guide

You can run `cli` commands by running `yarn ts-node <commands>`.

&#x20;    `i.e. yarn ts-node status`\


![Example command running](<../.gitbook/assets/image (1).png>)

Also can see the commands guide with `-h` option\


![Commands help guide](<../.gitbook/assets/image (2).png>)

{% hint style="info" %}
This command can only run in the _**`backend`**_ directory
{% endhint %}

To maintain the Staking Program as owner, you can use the `cli` commands in `./backend/cli/command.ts`

All commands' source scripts are in the `./backend/cli/scripts.ts` file.

## Configure script code

At first, you need to confirm all the configures.

`EPOCH` - reward generated time by second. This is used to calculate current available reward.

`USER_POOL_SIZE` - program's User PDA account size. This is used to create and rent the User PDA of Staking program. Calculated as following. You can check the User PDA structure [_here_](structure/data-layout.md#minimum-version-requirements-1)_._

&#x20;      `8 + 32 + 8 + 8 + 8 + (32 + 8) * STAKE_MAX_COUNT`

`REWARD_TOKEN_MINT` - reward token mint pubkey.

`REWARD_TOKEN_DECIMAL` - reward token decimal.

## Initialize Program

Before initialize program, you need to create the `Reward Token Associated Account` of the `Program's Global PDA` - `Reward Vault` . Initialize a program required you funds some amount of Reward token to the Program's Reward vault. So you should create RewardVault and funds some Reward token from somewhere.

You can do this by running `generate_reward_vault` command.

&#x20;   `yarn ts-node generate_reward_vault`

Then you should funds more than MIN\_REWARD\_DEPOSIT\_AMOUNT or Reward token to the Program's Global PDA Account.

You can get the Global PDA Address by running `yarn ts-node status` command.

![](<../.gitbook/assets/image (4).png>)

Now, you can initialize the Program by running `yarn ts-node init` command.



{% hint style="info" %}
Note that you should confirm the network connection cluster while running any command.

All commands have option to select cluster: `-e --env <string>` Default value: 'devnet'

Cluster string for devnet is _'devnet'_ and _'mainnet-beta'_ for mainnet.
{% endhint %}

## Debug cryptic errors ⚠️

If you get a cryptic error back that looks something like this:

```
Transaction failed 0x1798
```

The steps to take are as follows:

* translate the 0x number into decimal (eg using [this](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=0x66)) - eg 0x1798 becomes 6040
* if the number is 6XXX, this is a custom error from the app. Go to errors.rs found _here_ and find the error numbered 40 (the remainder of the decimal)
* any other number besides 6XXX means an anchor error - go _here_ to decipher it
