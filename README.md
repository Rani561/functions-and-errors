# TabletContract

TabletContract is a Solidity smart contract that allows users to purchase tablets and consume them as needed. The contract is deployed on the Ethereum blockchain.

## Features

- **Purchase Tablets:** Users can purchase tablets by specifying the desired quantity and sending the corresponding Ether. The tablets are added to the buyer's stock, and any excess Ether sent is refunded.
- **Consume Tablets:** Only the contract owner can consume tablets. The owner can specify the quantity to consume, ensuring they maintain control. An exception is thrown if an attempt is made to consume more than one tablet at a time.

## Contract Functions

### `purchaseTablet`

- **Function:** `purchaseTablet(uint256 count) external payable`
- **Description:** Allows users to purchase tablets by specifying the desired quantity and sending the corresponding Ether.
- **Modifiers:** 
  - `assert`: Ensures that the quantity is greater than 5.
- **Events:**
  - `TabletPurchased`: Emits an event when tablets are purchased, indicating the buyer's address and the quantity purchased.

### `consumeTablet`

- **Function:** `consumeTablet(uint256 count) external onlyOwner sufficientStock(count)`
- **Description:** Allows the contract owner to consume tablets by specifying the quantity to consume.
- **Modifiers:** 
  - `onlyOwner`: Restricts the function to be called only by the contract owner.
  - `sufficientStock`: Checks if the owner has sufficient tablets in stock to consume.
- **Revert Conditions:** 
  - Reverts the transaction if the quantity to consume is not equal to 1.
- **Events:**
  - `TabletConsumed`: Emits an event when tablets are consumed, indicating the owner's address and the quantity consumed.

## Deployment

The contract can be deployed on the Ethereum blockchain using any Ethereum-compatible development environment or platform such as Remix, Truffle

## License

This contract is licensed under the MIT License.

## Author 

rani561207@gmail.com

