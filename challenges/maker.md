# Maker

[Maker for dummies](https://medium.com/cryptolinks/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90)

## Challenges

### CDP pre-liquidator
In Maker ecosystem, your [CDP](https://crypviz.io/knowledge-database/collateralized-debt-position/) automatically gets liquidated when its collateralization level gets below 150%. This means 13% penalty on the collateralized funds, which is pretty bad. The idea is to create a set of smart contracts that would hold DAI and close your CDP before its collateralization reaches 150%, and then take smaller fee than 13%. Your smart contract’s DAI should be funded by a community of investors that would later earn a fee from “saved” CDPs.

### Lending platform holding NFTs as collateral
Use non-fungible tokens as collateral to borrow DAI. Value of exact token should be determined in the process of an auction (for example, a reverse dutch auction).

### Typescript typings for DAI.js
[dai.js](https://github.com/makerdao/dai.js) is currently missing typescript types definitions. Create as strict and helpful types as possible by using string literals, union types, and strict event emitters.

### Keepers re-implementation using DAI.js
The Maker system provides various opportunities for profit which help to maintain market equilibrium. Strategies to arbitrage these opportunities can be codified as keepers - automated bots which can detect and trade inefficiencies across Dai Core, OasisDEX and various other exchanges.

[Here](https://developer.makerdao.com/keepers/) you can read more currently exisitng keepers. Re-implement one of those in node.js using DAI.js!

### Better visualisation tools for MAKER ecosystem
Create tools that help exploring MAKER ecosystem. You might want to use [maker dashboard](https://dai.makerdao.com/) and [MKR Tools](https://mkr.tools/)) as inspiration.
