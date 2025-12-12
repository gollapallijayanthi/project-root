#  NFT Collection – ERC-721 Smart Contract with Full Automated Test Suite

This repository contains my implementation of an **ERC-721 NFT Smart Contract**, built using **Solidity** and tested thoroughly with **Hardhat**, **Mocha**, and **Chai**.
The project is fully Dockerized, enabling evaluators to run the entire test suite — **without installing Node.js or Hardhat** — using a single command.

---

##  Requirements

* Node.js 18+
* Docker (recommended for evaluators)

---

##  Local Setup

```bash
npm install
npx hardhat test
```

---

#  Project Overview

This project implements a **secure, standards-compliant NFT contract** designed for small-scale collections.
The contract enforces correct ownership rules, secure minting, supply limits, metadata handling, and precise state management.
A complete automated test suite verifies correct behavior across all valid and invalid scenarios.

To ensure a reproducible environment, all tests can also be executed inside a Docker container:

```bash
docker run --rm jayanthigollapalli10/nft-contract:latest
```

---

#  Key Features

###  Secure Minting

* Only the **contract owner** can mint new tokens
* Enforces a strict **maximum supply**
* Rejects invalid tokenIds and zero-address mints
* Prevents double-minting

###  Metadata via tokenURI

* Clean base URI pattern
* ERC-721-compatible `tokenURI()` behavior

###  Transfers & Ownership

* Supports:

  * `transferFrom`
  * `safeTransferFrom`
  * `approve`
  * `setApprovalForAll`
* Accurate balance and ownership updates

###  Pausable Minting

* Owner can pause/unpause mint operations

###  Burn Support

Burning a token correctly updates:

* Ownership
* Balances
* Approvals
* Total supply

###  Fully Automated Test Suite

Covers all major behaviors:

* Minting (valid + invalid)
* Transfers
* Approvals & operator approvals
* Burn logic
* Supply enforcement
* Zero-address & invalid token handling
* Unauthorized actions
* Gas usage expectations

 All **16 tests pass** locally and in Docker.

---

#  Project Structure

```
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
│
├── package.json
├── package-lock.json
├── hardhat.config.js
│
├── README.md
└── SUBMISSION.md
```

---

#  Running Tests Locally

### Install dependencies:

```bash
npm install
```

### Compile contracts:

```bash
npx hardhat compile
```

### Run tests:

```bash
npx hardhat test
```

Expected result:

```
16 passing
```

---

#  Running Tests with Docker (Recommended)

### Build the image:

```bash
docker build -t nft-contract .
```

### Run tests:

```bash
docker run --rm nft-contract
```

### Or use the published image:

```bash
docker pull jayanthigollapalli10/nft-contract:latest
docker run --rm jayanthigollapalli10/nft-contract:latest
```

---

#  Contract Highlights

* Built on OpenZeppelin’s ERC-721 standard
* Simple owner-only access control
* Clean metadata handling
* Reliable error messages & reverts
* Efficient state updates
* Correct event emissions
* Burn functionality with cleanup
* Pausable minting mechanism

---

#  Submission Contents

Includes everything needed for evaluation:

* `NftCollection.sol` contract
* Full test suite (`NftCollection.test.js`)
* Dockerfile (self-contained test runner)
* Hardhat config files
* `.dockerignore`
* `submission.zip`
* `SUBMISSION.md` evaluator instructions

---

#  Important Links

###  GitHub Repository

[https://github.com/gollapallijayanthi/project-root](https://github.com/gollapallijayanthi/project-root)

###  Docker Hub Image

[https://hub.docker.com/r/jayanthigollapalli10/nft-contract](https://hub.docker.com/r/jayanthigollapalli10/nft-contract)

---

#  Task Summary 

This project demonstrates my ability to design, implement, and validate a secure ERC-721 NFT contract using modern tooling and best practices. I built a fully functional NFT collection contract with strict supply control, reliable ownership mechanics, and metadata support. I complemented the implementation with a comprehensive automated test suite that validates correct behavior under normal, edge-case, and failure scenarios. To ensure reproducibility and ease of evaluation, the entire environment is Dockerized so that all tests can run with a single command. The final result is a clean, well-structured, standards-compliant NFT system ready for automated assessment.

---
