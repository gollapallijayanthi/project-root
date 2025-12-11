# NftCollection — ERC-721 NFT Smart Contract
A complete ERC-721 NFT smart contract built using Solidity, tested with Hardhat, and fully containerized using Docker.
This project demonstrates secure NFT design, ownership tracking, approvals, transfers, minting rules, and automated testing.

## Features

ERC-721–compatible NFT contract
Owner-only minting with max supply validation
Pause/unpause minting
Safe transfers + approvals + operator approvals
Token metadata via baseURI
Burn support with consistent state updates
Comprehensive automated test suite
Fully Dockerized test environment

## Project Structure
project-root/
│
├── contracts/
│   └── NftCollection.sol        
│
├── test/
│   └── NftCollection.test.js    
│
├── Dockerfile                    
├── .dockerignore                 
├── hardhat.config.js            
├── package.json
├── package-lock.json
└── README.md

## Testing
Run locally:
npm install
npx hardhat test

Run inside Docker:
docker build -t nft-contract .
docker run --rm nft-contract

All tests run automatically inside the container.
Contract Capabilities
Unique token ownership
Safe transfer mechanics
Prevents double minting
Rejects invalid token IDs
Tracks balances and totalSupply
Approval + operator approval workflows
Burn tokens safely
Emits all required ERC-721 events

## Docker Support

The included Dockerfile:

Installs dependencies
Compiles the contract
Runs all tests
Requires no external network access
Run it anywhere for consistent results.

## Summary
This project provides a clean, secure, and well-tested ERC-721 NFT implementation with a reproducible Docker environment.
It fulfills all requirements for NFT logic, testing, and containerization.
