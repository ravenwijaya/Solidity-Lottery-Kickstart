# Lottery Smart Contract

A simple Ethereum-based lottery smart contract written in Solidity. This contract allows users to enter a lottery by sending a small amount of Ether, and at the end of the game, the contract selects a winner randomly.

## Features

- **Manager Role**: Only the contract's creator (manager) can select the winner.
- **Entry Requirement**: Participants must send more than 0.01 ether to enter the lottery.
- **Random Winner Selection**: The winner is picked using a random function based on the current block's difficulty, timestamp, and the players' addresses.
- **Reset After Winner**: After a winner is picked, the list of players is reset for the next lottery.

## How to Use

1. Deploy the contract on the Ethereum blockchain.
2. The contract creator will be assigned as the `manager`.
3. Players can enter the lottery by sending more than 0.01 ether to the contract using the `enter` function.
4. After the lottery is complete, the manager can pick a winner using the `pickWinner` function, transferring the contract's balance to the winner.

## Code Overview

### Constructor
The contract's constructor sets the creator as the manager.

### enter()
Players can enter the lottery by sending a minimum of 0.01 ether. The `enter` function ensures that players cannot enter with less than the specified amount.

### random()
This private function generates a pseudo-random number based on the block's difficulty, timestamp, and the players' addresses. This number is used to select the winner.

### pickWinner()
The manager can pick a winner by calling this function. It selects a winner randomly from the players and transfers the contract's balance to them.

### restricted Modifier
This modifier ensures that only the contract's manager can call certain functions, like picking the winner.

### getPlayers()
This function allows anyone to view the list of players entered into the lottery.

## Prerequisites

- Ethereum wallet (e.g., MetaMask)
- Solidity 0.4.17 or higher

## License

This project is open-source and available under the MIT License.

