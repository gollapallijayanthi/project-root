# NftCollection – ERC-721 NFT Contract

## Requirements

- Node.js 18+
- Docker (for containerized tests)

## Local Setup

```bash
npm install
npx hardhat test



# NFT Collection – ERC-721 Smart Contract with Full Automated Test Suite

This repository contains my implementation of an **ERC-721 NFT Smart Contract** built using **Solidity & Hardhat**, packaged with a **Dockerized test runner** for fully reproducible evaluation.

It covers all required NFT behaviors—including secure minting, ownership tracking, transfers, approvals, metadata handling, and enforcing maximum token supply—along with a **comprehensive automated test suite** that validates correct behavior under both valid and error scenarios.

---

##  Overview

The goal of this project was to design a **secure, standards-compliant NFT contract** that supports a small NFT collection with predictable behavior, strong access control, and complete test coverage.

To ensure reproducibility, the entire environment is encapsulated in a Docker image. Evaluators can run:

```bash
docker run --rm jayanthigollapalli10/nft-contract:latest
```

and instantly execute all tests without installing Node.js, Hardhat, or dependencies.

---

##  Key Features

###  Secure Minting

* Only the **contract owner** can mint.
* Enforces a strict **maximum supply**.
* Prevents double-minting of the same token.
* Reverts on invalid tokenIds or zero-address mints.

### Metadata & TokenURI

* Base URI pattern for consistent metadata.
* `tokenURI()` validated & fully ERC-721-compatible.

### Transfers & Ownership

* Complete support for:

  * `transferFrom`
  * `safeTransferFrom`
  * `approve`
  * `setApprovalForAll`
* Accurate balance and ownership updates.

###  Pausable Minting

* Owner can **pause/unpause** minting operations.

###  Burn Support

* Burning tokens updates:

  * Ownership
  * Balances
  * Approvals
  * Total supply

###  Comprehensive Test Suite

All major operations tested:

* Minting (valid + invalid)
* Transfers
* Approvals + operator approvals
* Burn behavior
* Max supply enforcement
* Zero-address restrictions
* Reverts for unauthorized callers
* Gas usage sanity check

All **16 tests pass** both locally and inside the Docker container.

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

### Run all tests:

```bash
npx hardhat test
```

Expected output:

```
16 passing
```

---

#  Running Tests with Docker (Recommended)

### Build the image:

```bash
docker build -t nft-contract .
```

### Run tests inside container:

```bash
docker run --rm nft-contract
```

### Or pull my prebuilt image:

```bash
docker pull jayanthigollapallii10/nft-contract:latest
docker run --rm jayanthigollapallii10/nft-contract:latest
```

This runs the entire suite automatically with no configuration needed.

---

#  Contract Highlights (Based on My Implementation)

* OpenZeppelin ERC-721 base used for reliability.
* Access control via simple owner pattern.
* Exact revert reasons for invalid operations.
* Efficient state updates for ownership & transfers.
* Constructor initializes name, symbol, and max supply.
* Clean token enumeration and metadata lookup.
* Burn removes token ownership and approvals.
* Pausable minting ensures controlled supply rollout.

---

# 📦 Submission Contents

My submitted files include:

* `contracts/NftCollection.sol` – smart contract
* `test/NftCollection.test.js` – complete automated test suite
* `Dockerfile` – builds reproducible testing environment
* `.dockerignore` – speeds up Docker builds
* Hardhat configuration & package files
* `submission.zip` containing the required source tree
* `SUBMISSION.md` with evaluator instructions

---

#  Important Links

###  GitHub Repository

[https://github.com/gollapallijayanthii/project-root](https://github.com/gollapallijayanthii/project-root)

###  Docker Hub Image

[https://hub.docker.com/r/jayanthigollapallii10/nft-contract](https://hub.docker.com/r/jayanthigollapallii10/nft-contract)

---

# 🎯 Summary

This project delivers:

* A **fully functional ERC-721 NFT contract**
* **Secure, controlled minting** with supply limits
* **Comprehensive Hardhat test suite**
* **Reproducible Docker environment**
* **Clean code**, predictable behavior, strong invariants
* A ready-to-evaluate submission package

