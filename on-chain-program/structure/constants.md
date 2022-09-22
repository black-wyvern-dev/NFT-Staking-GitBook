---
description: On-chain program's configure values which configured while deployment.
---

# Constants

You can check the Staking Program's constants values in `./backend/programs/Mutable_Staking/src/constants.rs` file.



| Field                        | Description                                                                                   | Type  |
| ---------------------------- | --------------------------------------------------------------------------------------------- | ----- |
| STAKE\_MAX\_COUNT            | max NFTs count able to stake from one wallet                                                  | usize |
| MAX\_ALLOWED\_COUNT          | max whitelist count able to change the reward\_rate   after deploy the program                | usize |
| EPOCH                        | reward generated period by second                                                             | i64   |
| COLLECTION\_ADDRESS          | creator address of NFT collection                                                             | \&str |
| REWARD\_TOKEN\_MINT\_PUBKEY  | reward token mint pubkey                                                                      | \&str |
| GLOBAL\_AUTHORITY\_SEED      | Global PDA's seed; _Don't need to change for your deployment_                                 | \&str |
| MIN\_REWARD\_DEPOSIT\_AMOUNT | Minimum deposit amount to reward vault of program; _Don't need to change for your deployment_ | u64   |

****

