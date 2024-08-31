# Token System Simulation

This project is a basic simulation of a token system, implemented in JavaScript. The code allows you to mint and burn tokens, check balances, and track the total supply of a custom token. It mimics the behavior of smart contracts typically found on blockchain platforms like Ethereum.

## Features

- **Mint Tokens**: Increase the total supply and the balance of a given address.
- **Burn Tokens**: Decrease the total supply and the balance of a given address, with checks to prevent burning more tokens than are available.
- **Check Balances**: Retrieve the token balance of any address.
- **Total Supply**: Get the current total supply of the token.

## Code Overview

### `Token` Class

The `Token` class is the core of this simulation. It handles all the operations related to minting, burning, and tracking tokens.

- **Constructor**: Initializes the token with a name, symbol, and sets the initial total supply to zero.
- **mint(address, amount)**: Mints new tokens, increasing both the total supply and the balance of the specified address.
- **burn(address, amount)**: Burns tokens, decreasing both the total supply and the balance of the specified address. Includes a check to ensure the balance is sufficient.
- **balanceOf(address)**: Returns the balance of the specified address.
- **getTotalSupply()**: Returns the current total supply of the token.

### Example Usage

The provided code includes an example usage of the `Token` class, where tokens are minted, balances are checked, tokens are burned, and the total supply is displayed.

```javascript
// Create an instance of the Token class
const myToken = new Token("MyToken", "MTK");

// Mint some tokens
myToken.mint("0x123", 100);
myToken.mint("0x456", 50);

// Check balances
console.log(`Balance of 0x123: ${myToken.balanceOf("0x123")} MTK`);
console.log(`Balance of 0x456: ${myToken.balanceOf("0x456")} MTK`);

// Burn some tokens
myToken.burn("0x123", 30);
myToken.burn("0x456", 60); // This should trigger an insufficient balance warning

// Check balances again
console.log(`Balance of 0x123: ${myToken.balanceOf("0x123")} MTK`);
console.log(`Balance of 0x456: ${myToken.balanceOf("0x456")} MTK`);

// Display total supply
console.log(`Total Supply: ${myToken.getTotalSupply()} MTK`);
