# Multi-Signature Wallet Dapp

## About this exercise

A multisignature wallet is an account that requires some m-of-n quorum of approved private keys to approve a transaction before it is executed.

## Pre-requisites and programs used versions:

- Truffle v5.1.7 (core: 5.1.7)
- Solidity v0.5.12 (solc-js)
- Node v10.17.0
- Web3.js v1.2.1
- npm 6.11.3
- Ganache CLI v6.7.0 (ganache-core: 2.8.0)
- MetaMask V7.7.3
- Openzeppelin

## Setting up the development environment

1. Install Truffle: 
    >npm install -g truffle

2. Install ganache-cli:
    >npm install -g ganache-cli

3. Install MetaMask in your browser (https://metamask.io/)

4. Install Openzepplin testing package*
    >npm install @openzeppelin/text-helpers

* Note: (4) Truffle has already an integrated debugger, so it is optional to install external testing API.

## Installation/Running

**Launching local blockchain with Ganache**

First launch the local testing blockchain with 10 default testing accounts which contains ETH.
Open up a new seperate terminal, and run the following command:

    >truffle develop

New blockchain listens on **127.0.0.1:9545** by default
Copy the MNEMONIC seed to Metamask and connect Metamask as "LocalHost 9545" on the port listed above.

**In order to keep development environment running, do not close this terminal**

**Clone the project**

Open up another new terminal, make sure the development terminal is running at the same time.

1. git clone https://github.com/cherylkw/multisigwallet.git

2. Move to the directory
    >npm install

3. Move to "client" directory
    >npm install web3

4. Compile the contracts
    >truffle compile

5.  Migrate to development enviornment
    >truffle migrate --reset

6. Run tests. (All tests should pass)
    >truffle test

7. Run Dapp, move to client folder
    >npm start

## Visiting an URL and interact with the application

- http://localhost:3000/
- This Dapp requires to interact with MetaMask. When the dapp loaded, MetaMask pop-up will appear if installed properly, requesting your approveal to allow Dapp connect to MetaMask wallet. Please choose **Connect**.

### Deploy to Kovan testnet

1. Generate 3 Ethereum vanity addresses @ https://vanity-eth.tk/ , in this exercise we use 3 accounts and 2 quroum to run the Dapp. Make sure to save eacb address with its private key

2. Get fake ETH to deploy and interact with the smart contract @ https://faucet.kovan.network/

3. Check if the address recieved testing ETH @ https://kovan.etherscan.io/

4. Create project @ infura for deployment on public testnet and mainnet, copy the testnet/mainnet URL 

5. Config truffle project to use infura:
    - in project folder : npm install @truffle/hdwallet-provider
    - config truffle-config.js

6. Deploy smart contract to Kovan public testnet
    >truffle migrate --reset --network kovan

7. Deploy frontend Dapp on server, this time to use:  https://www.netlify.com/
    - create testing account (import private key from the first address) in metamask under Kovan network
    - cd client
    - build the frontend, pack the frontend code into a javascript file to deploy : npm run build
    - login to account, drag and drop build folder in client folder
    - generate an url https://dreamy-swartz-83474f.netlify.app

### Deploy to mainnet

Same steps as deploying to testnet

- In Infura, select "mainnet" to get the correct endpoint
- In `truffle-config.js` file, update the Infura endpoint url to the one for mainnet
- Buy some Ether at an exchange to run the Dapp





