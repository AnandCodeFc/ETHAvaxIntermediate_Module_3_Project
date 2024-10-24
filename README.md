# Metacrafters Types Of Function Module Project 

### Module Objective 

Write a smart contract to create your own ERC20 token and deploy it using HardHat or Remix. Once deployed, you should be able to interact with it for your walk-through video. From your chosen tool, the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens

### Introduction

MyToken is an ERC20 token built using the Solidity programming language and the OpenZeppelin library. This smart contract allows users to mint, burn, and transfer tokens, as well as approve others to spend tokens on their behalf.

## Features

- **Minting:** Allows users to create new tokens and assign them to an address.
- **Burning:** Enables users to burn tokens from their own balance.
- **Transfer:** Users can transfer tokens to other addresses.
- **Approval:** Users can approve a specified address to spend tokens on their behalf.

## Prerequisites

- [Solidity ^0.8.10](https://soliditylang.org/)
- [OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/4.x/)

Make sure to have the OpenZeppelin ERC20 contract installed:

```bash
npm install @openzeppelin/contracts
```

## Contract Overview

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.10;

// Import OpenZeppelin contracts
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    
    // The constructor initializes the token with its name and symbol.
    constructor(string memory name, string memory symbol) ERC20(name, symbol) {}

    /**
     * @dev Mints new tokens.
     * @param to The address that will receive the minted tokens.
     * @param amount The number of tokens to mint.
     */
    function mint(address to, uint256 amount) public  {
        _mint(to, amount);
    }

    /**
     * @dev Burns tokens from the caller's account.
     * @param amount The number of tokens to burn.
     */
    function burn(uint256 amount) external {
        _burn(msg.sender, amount);
    }

    /**
     * @dev Transfers tokens to a specified address.
     * @param to The address to transfer to.
     * @param amount The amount of tokens to be transferred.
     * @return A boolean value indicating whether the operation succeeded.
     */
    function transfer(address to, uint256 amount) public override returns (bool) {
        return super.transfer(to, amount);
    }

    /**
     * @dev Approves the passed address to spend the specified amount of tokens on behalf of the caller.
     * @param spender The address that will spend the tokens.
     * @param amount The amount of tokens to be spent.
     * @return A boolean value indicating whether the operation succeeded.
     */
    function approve(address spender, uint256 amount) public override returns (bool) {
        return super.approve(spender, amount);
    }
}
```

### Constructor

The constructor initializes the ERC20 token with a name and symbol.

```solidity
constructor(string memory name, string memory symbol) ERC20(name, symbol) {}
```

### Functions

#### `mint(address to, uint256 amount)`

Mints a specified number of tokens and assigns them to the given address.

- **Parameters:**
  - `to`: The address that will receive the minted tokens.
  - `amount`: The number of tokens to mint.

#### `burn(uint256 amount)`

Burns a specified number of tokens from the caller's account, reducing the total supply.

- **Parameters:**
  - `amount`: The number of tokens to burn.

#### `transfer(address to, uint256 amount)`

Transfers tokens from the caller's account to a specified address.

- **Parameters:**
  - `to`: The address to transfer to.
  - `amount`: The number of tokens to transfer.

- **Returns:** A boolean indicating whether the transfer was successful.

#### `approve(address spender, uint256 amount)`

Allows the `spender` address to withdraw tokens from the caller's account up to the specified `amount`.

- **Parameters:**
  - `spender`: The address that will spend the tokens.
  - `amount`: The number of tokens the spender is allowed to spend.

- **Returns:** A boolean indicating whether the approval was successful.

## Deployment

1. Clone this repository:

   ```bash
   git clone <repository-url>
   ```

2. Install the required dependencies:

   ```bash
   npm install
   ```

3. Compile the contract:

   ```bash
   click To Compile Button
   ```

4. Deploy the contract using your preferred network configuration.

This README provides a comprehensive overview of the `MyToken` contract, its functionality, and deployment steps. Adjust the content according to your specific needs or repository details.
