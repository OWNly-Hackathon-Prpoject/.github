# OWNly Project - hack the mountain hackathon
Allows to support content creators from twitter to interact with their followers and have additional support by mintable tweets.

## Table of content
- [OWNly Twitter - hack the mountain](#ownly-twitter---hack-the-mountain)
  - [Table of content](#table-of-content)
  - [UI](#ui)
  - [Frontend](#frontend)
  - [Contracts](#contracts)
    - [Overview](#overview)
    - [Tests](#tests)
    - [Deployed Contract](#deployed-contract)
    - [Deployed NFTs](#deployed-nfts)

## UI

###

## Frontend

###

## Contracts

### Overview
Contract allows to mint ERC721 NFT with metadata from `NFT.storage` API. Content creator can easily deploy their valuable tweets with customizable fees and supply. Followers in order to support the creator can mint the NFT paying some fee (established by content creator). Users can use their personal balance in vault for paying for transactions without any signing of transaction. This abstraction allows for users to only send in some bulk amount to vault once in a while to prevent having to always sign transaction using a provider.

### Tests
The [integration test](https://github.com/OWNly-Hackathon-Prpoject/contracts/tree/main/test/integration) imitates well, how the general flow looks like:
1. Contract owner can set some deploy fee
2. Tweet with certain ID is loaded to the website - this case ID 1844 is assumed
3. Content creator deploys his tweet with some certain parameters - pays minor fee from his vault or inludes fee in transaction.
4. Follower mints deployed tweet with customizable image - pays fee established by content creator from his vault or inludes fee in transaction.
5. Some basic metadata about tweet and customized image is stored in IPFS via `NFT.storage` API
6. URI to this metadata is stored in the blockchain 

<img src=./images/contracts/Tests.png alt="drawing" width="720" height="210"/>

### Deployed Contract
The contract is fully verified and visible on [Polygonscan](https://mumbai.polygonscan.com/address/0x4c629d4f72fc89cc2ca1650994429bcd91c3d99c). Once tests are performed [here](#tests), you can see some results in polygonscan:

<img src=./images/contracts/FunctionExampleOwnerOf.png alt="drawing" width="800" height="140"/>

<img src=./images/contracts/FunctionExampleTweetId.png alt="drawing" width="800" height="140"/>

<img src=./images/contracts/FunctionExampleURI.png alt="drawing" width="800" height="140"/>

### Deployed NFTs
The followers should see minted NFTs on OpenSea thanks to compatible URI and metadata:

<img src=./images/contracts/NFT.png alt="drawing" width="850" height="900"/>



