# Data Layout

You can check the Staking Program's accounts layout in `./backend/programs/Mutable_Staking/src/account.rs` file.

## Global Pool Account <a href="#minimum-version-requirements" id="minimum-version-requirements"></a>



| Field                | Description                                                       | Type                           |
| -------------------- | ----------------------------------------------------------------- | ------------------------------ |
| super\_admin         | program owner                                                     | Pubkey                         |
| reward\_rate         | reward amount for each NFT                                        | u64                            |
| total\_staked\_count | total staked NFTs count in the program                            | u64                            |
| whitelisted\_count   | whitelisted wallet addresses count                                | u64                            |
| whitelist            | wallet addresses whitelisted to change the **reward\_rate** value | \[Pubkey; MAX\_ALLOWED\_COUNT] |

****

## User Pool Account <a href="#minimum-version-requirements" id="minimum-version-requirements"></a>



| Field              | Description                        | Type                             |
| ------------------ | ---------------------------------- | -------------------------------- |
| owner              | staker wallet pubkey               | Pubkey                           |
| last\_reward\_time | blocktime of last claimed time     | i64                              |
| pending\_reward    | generated reward for unstaked NFTs | u64                              |
| staked\_count      | staked NFT count from this user    | u64                              |
| staked\_nfts       | info for individual staked NFTs    | \[StakedData; STAKE\_MAX\_COUNT] |



#### StakedData structure

| Field        | Description               | Type   |
| ------------ | ------------------------- | ------ |
| mint         | staked NFT mint pubkey    | Pubkey |
| staked\_time | blocktime when NFT staked | i64    |

