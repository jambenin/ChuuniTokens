# ChuuniTokens

A simple ERC20 token contract that includes mint and burn functionalities, designed to allow users to mint new tokens and burn existing ones.

## Description

ChuuniTokens is a smart contract created on the Ethereum blockchain that mimics the functionality of an ERC20 token. The contract supports two main actions: **minting** new tokens and **burning** tokens. 

## Getting Started

### Installing

1. Go to [Remix IDE](https://remix.ethereum.org/).
2. Open a new workspace and paste the contract code from `ChuuniTokens.sol` (provided below) into a new Solidity file in Remix.
3. There are no modifications needed to the code as it's already set up to work.

### Executing the Program

#### Step-by-step guide:

1. **Open Remix IDE**: Go to [Remix Ethereum IDE](https://remix.ethereum.org/).
2. **Create a new file**: Click on the "File Explorer" in Remix and create a new file (e.g., `ChuuniTokens.sol`).
3. **Paste the contract code**: Copy the following code into the file.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract ChuuniTokens {
    string public tokenName = "ChuuniTokens";
    string public tokenSymbol = "CHUUNI";
    uint public totalSupply;

    mapping(address => uint) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    // Burn function to destroy tokens
    function burn(address _from, uint _value) public {
        require(balances[_from] >= _value, "Insufficient balance to burn.");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}

