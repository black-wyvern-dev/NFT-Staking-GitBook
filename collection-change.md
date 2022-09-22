# 🎢 Collection change

To stake your NFT collection by deploying your staking program, you need to change the COLLECTION\_CREATOR address on both of Program and Website side.

## Backend side

The Staking Program will validate if the staking NFT's creator address is same with the COLLECTION\_CREATOR value.\
So other collection NFT's staking will always failure.

For that, you should change the `COLLECTION_CREATOR` address before deploying your Own Staking Program. You can find the `COLLECTION_CREATOR` value in the  `./backend/programs/Mutable_Staking/src/constants.rs` file.

![](<.gitbook/assets/image (5).png>)

## Frontend side

Change the `COLLECTION_CREATOR` address  in `./frontend/src/config.tsx` file.

![](<.gitbook/assets/image (3).png>)

**Effect:**

* This will show only your collection NFTs in the connected wallet
* Able to stake your collection NFTs
