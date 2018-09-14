# Maker

[Maker for dummies](https://medium.com/cryptolinks/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90)

## CDP pre-liquidator
In Maker ecosystem, your [CDP](https://crypviz.io/knowledge-database/collateralized-debt-position/) automatically gets liquidated when its collateralization level gets below 150%. This means 13% penalty on the collateralized funds, which is pretty bad. The idea is to create a set of smart contracts that would hold DAI and close your CDP before its collateralization reaches 150%, and then take smaller fee than 13%. Your smart contract’s DAI should be funded by a community of investors that would later earn a fee from “saved” CDPs.

## Lending platform holding NFTs as collateral
Use non-fungible tokens as collateral to borrow DAI. Value of exact token should be determined in the process of an auction (for example, a reverse dutch auction).

## Typescript typings for DAI.js
[dai.js](https://github.com/makerdao/dai.js) is currently missing typescript types definitions. Create as strict and helpful types as possible by using string literals, union types, and strict event emitters.

## Keepers re-implementation using DAI.js
The Maker system provides various opportunities for profit which help to maintain market equilibrium. Strategies to arbitrage these opportunities can be codified as keepers - automated bots which can detect and trade inefficiencies across Dai Core, OasisDEX and various other exchanges.

[Here](https://developer.makerdao.com/keepers/) you can read more currently exisitng keepers. Re-implement one of those in node.js using DAI.js!

## Better visualisation tools for MAKER ecosystem
Create tools that help exploring MAKER ecosystem. You might want to use [maker dashboard](https://dai.makerdao.com/) and [MKR Tools](https://mkr.tools/)) as inspiration.

# Tokens

## Implement one of the new ERC token standards
While ERC20 and ERC721 are very well known, there are some other token standards that had little adoption so far:

* ERC 621 allows for the modification of totalSupply
* ERC 804 separation of voting rights from the tokens
* ERC 1203 multi-class tokens (i.e. multiple ERC20 tokens on one contract, ERC 721 style)
* ERC 1404 security token (aka SRS-20)

Build something like [TokenFactory](https://tokenfactory.surge.sh/), but implementing one of these standards.

## Token metadata viewer
There is a lot of data related to tokens and contracts floating around off-chain. Websites/Social media links related to the contract owners, logos and so on. There is an open-source list of such metadata here: https://github.com/ethereum-lists/Methadata - the current interface is far from perfect, and it would be nice to have a browser for it, perhaps with an option to submit extra information.

## Tokens issued/distributed by oracles
Right now, the majority of tokens are issued and distributed by on-chain mechanisms: auctions, airdrops, ICOs.

Build a new token that is issued by an oracle based on specific criteria. Examples:
An oracle/daemon that watches Wikipedia editor pages, and issues THANK-YOU tokens to all the editors that publish an ethereum address on their page
An oracle/webserver that awaits an upload of an image, and if the image is uploaded, releases an ERC-721 token associated with it
A simple web game that releases tokens as points in the game (this might require POA for cheaper transactions, and may tie in nicely with Hoard.Exchange)

## Token recycler ;)
There is a growing issue of trash tokens - the ones airdropped en masse, ones from failed ICOs, or past-their prime Cryptokittens.

It would be useful to have a contract that accepts all the ERC-20 and ERC-721 tokens, and recycles them into some new kind of a token. For example, the user deposits 100 DAO, 500 AIRDRP, and four old CryptoKitties, and received 1000 RECYCLE tokens - just as useless, but so much neater! :)

<!-- HINT: Look at gas usage  -->

# Contract design

## Probabilistic transaction settlement
Scenario:
 * Blockchain system - final, atomic transactions
 * FIAT system - not final, possible partial transfer of funds
 * probability p of transfer finality
 * Underwriting fiat assets transactions

# Oracles

## Open Banking meets blockchain
Use Open Banking (think bank database read/write access) to connect bank world with blockchain one.

### Use cases
 * copy Tether system
 * be your own Tether (CEB - cebulion token network)
 * build Ramp
 * api wrapper smart contract <-> OBP - programming money

### Technical details

Connect to OBP APIs and set up an oracle that gets data from https://openbankproject.com/
You can use:
 * Official OBP sandbox - https://apisandbox.openbankproject.com/
 * Sandbox hosted by us at: 169.197.100.205:8080
 * Local docker container - https://github.com/OpenBankProject/OBP-Docker (remember about configuration)

OBP wiki: https://github.com/OpenBankProject/OBP-API/wiki/Sandbox

You can use Direct Login: https://github.com/OpenBankProject/OBP-API/wiki/Direct-Login

## Official institutions’ data oraclised
There is abundance of rubbish data available, but interesting one, are semi-closed in previous-era public digital systems.

Fortunately we can have access to them through API created by NGOs.

Create oracle publishing data to blockchain:
 * KRS, NBP, GPW, polish institutions oracles - https://mojepanstwo.pl/api/krs
 * Sejm - https://mojepanstwo.pl/api/sejmometr
 * eu parliament votes
 * other...

Then, on top of that, create blockchain application using public data. Ideas:
 * prediction market
 * liquid democracy system (or other governance system) - imagine you can influence votes of one (or group of) MP - how you could ensure
 * ICO

# Exchange
## Create NFT exchange / auction system

How to create exchange on illiquid, non fungible tokens with effective price discovery mechanism?
How to implement effective order matching solution in this case?

Possible angles:
 * Use etherdelta system
 * Reverse dutch auction - eg. you may use DutchX sourcecode
 * Hybrid off/onchain system
 * Generalise cryptokitties auction mechanism
 * How to predict price of such asset - price feeds
 * Data visualisation of real NFT auctions
 * ...


