## CDP pre-liquidator
In Maker ecosystem, your CDP automatically gets liquidated when it’s collateralization level gets below 150%. This means 13% penalty on the collateralized funds which is pretty bad. The idea is to create a set of smart contracts that would hold DAI and close your CDP before it’s collateralization reaches 150% and then take smaller fee then 13%. Your smart contract’s DAI should be funded by a community of investors that would later earn fee from “saved” CDPs.

## Lending platform holding NFTs as collateral
Use non-fungible tokens as collateral to borrow DAI. Value of exact token should be determined in the process of an auction (for example reverse dutch auction).

## Typescript typings for DAI.js
[dai.js](https://github.com/makerdao/dai.js) is currently missing typescript types definitions. Create as strict and helpful types as possible by using string literals, union types, and strict event emitters.
