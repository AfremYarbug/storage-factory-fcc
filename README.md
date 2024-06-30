# About the Project

## Overview

`StorageFactory` is a smart contract built in Solidity that demonstrates how to deploy and manage multiple instances of another contract (`SimpleStorage`). It allows users to create, store, and interact with multiple `SimpleStorage` contracts, facilitating the organization and retrieval of stored data.

## Features

- **Contract Deployment**: Deploys new instances of the `SimpleStorage` contract.
- **Store Data**: Allows storing a favorite number in a specified `SimpleStorage` contract instance.
- **Retrieve Data**: Retrieves the stored favorite number from a specified `SimpleStorage` contract instance.

## Contracts

### StorageFactory

The `StorageFactory` contract manages an array of `SimpleStorage` contract instances and provides functions to interact with them.

#### State Variables

- `SimpleStorage[] public simpleStorageArray`: A dynamic array that holds instances of `SimpleStorage` contracts.

#### Functions

##### `createSimpleStorageContract() public`

Deploys a new instance of the `SimpleStorage` contract and adds it to the `simpleStorageArray`.

##### `sfStore(uint256 _simpleStorageIndex, uint256 _simpleStorageNumber) public`

Stores a given number in the specified `SimpleStorage` contract instance.

- **Parameters**:
  - `_simpleStorageIndex` (uint256): The index of the `SimpleStorage` contract instance in the `simpleStorageArray`.
  - `_simpleStorageNumber` (uint256): The number to be stored in the specified `SimpleStorage` contract instance.

##### `sfGet(uint256 _simpleStorageIndex) public view returns (uint256)`

Retrieves the stored number from the specified `SimpleStorage` contract instance.

- **Parameters**:
  - `_simpleStorageIndex` (uint256): The index of the `SimpleStorage` contract instance in the `simpleStorageArray`.
- **Returns**:
  - `uint256`: The stored favorite number.

### SimpleStorage

The `SimpleStorage` contract allows users to store, retrieve, and manage a favorite number along with names associated with favorite numbers.

#### State Variables

- `uint256 public favoriteNumber`: Stores the favorite number.
- `mapping(string => uint256) public nameToFavoriteNumber`: Maps names to their favorite numbers.
- `People[] public people`: A dynamic array that stores people and their favorite numbers.

#### Structs

- `People`: Defines a structure with two properties:
  - `favoriteNumber` (uint256): The favorite number of the person.
  - `name` (string): The name of the person.

#### Functions

##### `store(uint256 _favoriteNumber) public`

Updates the `favoriteNumber` variable with the provided input.

##### `retrieve() public view returns (uint256)`

Returns the current value of `favoriteNumber`.

##### `addPerson(string memory _name, uint256 _favoriteNumber) public`

Adds a new person to the `people` array and updates the `nameToFavoriteNumber` mapping.

### ExtraStorage

The `ExtraStorage` contract inherits from `SimpleStorage` and overrides the `store` function to add 5 to the input number before storing it.

#### Functions

##### `store(uint256 _favoriteNumber) public override`

Overrides the `store` function of `SimpleStorage` to add 5 to the input number before storing it.

## Usage

The `StorageFactory` contract can be deployed on the Ethereum blockchain. Once deployed, users can interact with it to create multiple `SimpleStorage` contracts, store values in them, and retrieve those values. This project showcases fundamental concepts of Solidity, such as contract deployment, inheritance, function overriding, and interaction between contracts.


# Lesson 3: Remix Storage Factory

_[⌨️ (03:05:34) Lesson 3: Remix Storage Factory](https://www.youtube.com/watch?v=gyMwXuJrbJQ&t=11134s)_

💻 Code: https://github.com/PatrickAlphaC/storage-factory-fcc

## Introduction

_[⌨️ (03:06:06) Introduction](https://youtu.be/gyMwXuJrbJQ?t=11166)_

- [Factory Pattern](https://betterprogramming.pub/learn-solidity-the-factory-pattern-75d11c3e7d29)

## Basic Solidity: Importing Contracts into other Contracts

_[⌨️ (03:07:29) Importing Contracts into other Contracts](https://youtu.be/gyMwXuJrbJQ?t=11249)_

### import a contract
`import "./SimpleStorage.sol"`

## Basic Solidity: Interacting with other Contracts

_[⌨️ (03:16:36) Interacting with other contracts](https://youtu.be/gyMwXuJrbJQ?t=11796)_

- To interact, you always need: ABI + Address
- [ABI](https://docs.soliditylang.org/en/latest/abi-spec.html?highlight=abi)

## Basic Solidity: Inheritance & Overrides

_[⌨️ (03:25:23) Inheritance & Overrides](https://youtu.be/gyMwXuJrbJQ?t=12323)_

- [Inheritance](https://solidity-by-example.org/inheritance)
- [Override & Virtual Keyword](https://docs.soliditylang.org/en/latest/contracts.html?highlight=override#function-overriding)

## Lesson 3 Recap

_[⌨️ (03:30:29) Lesson 3 Recap](https://youtu.be/gyMwXuJrbJQ?t=12629)_
