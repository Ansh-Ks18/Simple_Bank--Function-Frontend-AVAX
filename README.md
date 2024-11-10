# 🌐 Welcome to Simple Bank

> 💸 A Simple Web3 application for managing Ether transfers and account balances.

## Description

This project is an intuitive web3 application created using JavaScript and Solidity. It leverages the power of Ethereum networks to provide a decentralized banking experience. With this dApp, users can deposit and withdraw Ether, transfer funds to other accounts, and check their balances. The application is built using Solidity smart contracts, the Ethers.js library, and the MetaMask wallet extension.

## 🎥 Video Tutorial

For a detailed video walkthrough, watch the [video](https://www.loom.com/share/58d6a165ba22421599bbc6d107b1e566?sid=3c393a55-09ee-4f2a-841c-abca3bf1d77f).

FOR MORE DETAILED VIDEO VISIT HERE -> watch the [video](https://www.loom.com/share/9847ea79700d43b9b6b305f41a4a39b9?sid=9ee3ac56-2b1e-4d82-a772-741635e2fe45).

## Technologies Used 🛠️

![JavaScript](https://forthebadge.com/images/badges/made-with-javascript.svg) ![Ethereum](https://img.shields.io/badge/Ethereum-3C3C3D?style=for-the-badge&logo=Ethereum&logoColor=white) ![Web3.js](https://img.shields.io/badge/web3.js-F16822?style=for-the-badge&logo=web3.js&logoColor=white) ![Solidity](https://img.shields.io/badge/Solidity-%23363636.svg?style=for-the-badge&logo=solidity&logoColor=white) ![MetaMask](https://avatars.githubusercontent.com/u/11744586?s=48&v=4) ![Hardhat](https://hardhat.org/_next/static/media/hardhat-logo.5c5f687b.svg)

This project utilizes the following technologies:

- **Solidity**: Solidity is a programming language specifically designed for writing smart contracts on the Ethereum platform. It is used to write the `Simple_Bank` smart contract in this project. [Learn more about Solidity](https://docs.soliditylang.org/).

- **Ethers.js**: Ethers.js is a JavaScript library that provides a concise and consistent API for interacting with Ethereum and Ethereum-like networks. It is used to interact with the Ethereum blockchain and execute transactions in this project. [Explore Ethers.js](https://docs.ethers.org/v5/).

- **MetaMask**: MetaMask is a popular browser extension wallet that allows users to manage Ethereum accounts and interact with decentralized applications. It is used to connect to the Ethereum network and perform transactions in this project. [Get MetaMask](https://metamask.io/).

- **Hardhat**: Hardhat is a development environment and testing framework for Ethereum smart contracts. It provides tools for compiling, deploying, and testing contracts. Hardhat is used to compile and deploy the `Simple_Bank` smart contract in this project. [Discover Hardhat](https://hardhat.org/).

## Installation ⬇️

### Follow these steps to get the project up and running 🏗️

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/simple-bank.git
   ```
2. Install the dependencies:
   ```sh
   npm install
   ```
3. Start the local blockchain using Hardhat:
   ```sh
   npx hardhat node
   ```
4. Open a new terminal and deploy the `Simple_Bank` contract:
   ```sh
   npx hardhat run --network localhost scripts/deploy.js
   ```
5. Start the development server:
   ```sh
   npm run dev
   ```

### Configure MetaMask to use the Hardhat node 🦊

1. Open the MetaMask extension in your browser.
2. Click on the account icon in the top right corner and select "Settings".
3. In the "Networks" tab, click on "Add Network".
4. Fill in the following details:
   - **Network Name**: Localhost
   - **RPC URL**: http://127.0.0.1:8545/
   - **Chain ID**: 31337
   - **Currency Symbol**: ETH
5. Click on "Save" to add the Hardhat network to MetaMask.

### Add accounts using private keys provided by Hardhat for testing 🔑

1. In the MetaMask extension, click on the account icon in the top right corner.
2. Select "Import Account" or "Import Account using Private Key" (depending on your version of MetaMask).
3. In the "Private Key" field, enter one of the private keys provided by Hardhat.
   - To access the list of private keys, open the terminal where you started the Hardhat local network.
   - The private keys are displayed as part of the accounts generated by Hardhat.
4. Click on "Import" to import the account into MetaMask.
5. Repeat the above steps to add more accounts for testing purposes.

For more detailed instructions, refer to this step-by-step guide on [how to use MetaMask with a Hardhat node](https://support.chainstack.com/hc/en-us/articles/4408642503449-Using-MetaMask-with-a-Hardhat-node).

## Usage 🪜

**To use the application, follow these instructions:**

1. After connecting MetaMask to the Hardhat local network, connect your wallet with the application.
2. Click on the desired action (Deposit, Withdraw, Transfer) and enter the required details.
3. Confirm the transaction in MetaMask.
4. The transaction details will be logged to the console, and the account balance will be updated.

## Contract Details 🔗

The `Simple_Bank` smart contract located in `contracts/Simple_Bank.sol` allows users to deposit, withdraw, and transfer funds. It emits events (`Deposit`, `Transfer`, `Withdrawal`) for these actions.

```json
[
  {
    "inputs": [],
    "name": "deposit",
    "outputs": [],
    "stateMutability": "payable",
    "type": "function"
  },
  {
    "anonymous": false,
    "inputs": [
      {
        "indexed": true,
        "internalType": "address",
        "name": "account",
        "type": "address"
      },
      {
        "indexed": false,
        "internalType": "uint256",
        "name": "amount",
        "type": "uint256"
      }
    ],
    "name": "Deposit",
    "type": "event"
  },
  {
    "inputs": [
      {
        "internalType": "address",
        "name": "to",
        "type": "address"
      },
      {
        "internalType": "uint256",
        "name": "amount",
        "type": "uint256"
      }
    ],
    "name": "transfer",
    "outputs": [],
    "stateMutability": "nonpayable",
    "type": "function"
  },
  {
    "anonymous": false,
    "inputs": [
      {
        "indexed": true,
        "internalType": "address",
        "name": "from",
        "type": "address"
      },
      {
        "indexed": true,
        "internalType": "address",
        "name": "to",
        "type": "address"
      },
      {
        "indexed": false,
        "internalType": "uint256",
        "name": "amount",
        "type": "uint256"
      }
    ],
    "name": "Transfer",
    "type": "event"
  },
  {
    "inputs": [
      {
        "internalType": "uint256",
        "name": "amount",
        "type": "uint256"
      }
    ],
    "name": "withdraw",
    "outputs": [],
    "stateMutability": "nonpayable",
    "type": "function"
  },
  {
    "anonymous": false,
    "inputs": [
      {
        "indexed": true,
        "internalType": "address",
        "name": "account",
        "type": "address"
      },
      {
        "indexed": false,
        "internalType": "uint256",
        "name": "amount",
        "type": "uint256"
      }
    ],
    "name": "Withdrawal",
    "type": "event"
  },
  {
    "inputs": [],
    "name": "getBalance",
    "outputs": [
      {
        "internalType": "uint256",
        "name": "",
        "type": "uint256"
      }
    ],
    "stateMutability": "view",
    "type": "function"
  }
]
```

## Project Structure 📁

The project is organized into the following directories and files:

- **`contracts/`**: Contains the Solidity smart contracts.
  - `SimpleBank.sol`: The main smart contract for the Simple Bank application.
- **`scripts/`**: Contains scripts for deploying the smart contracts.
  - `deploy.js`: Script to deploy the SimpleBank contract.
- **`test/`**: Contains the test cases for the smart contracts.
  - `SimpleBank.js`: Test cases for the SimpleBank contract.
- **`public/`**: Contains public assets such as images and JavaScript files for the front-end application.
- **`src/`**: Contains the main JavaScript files for the front-end application.
  - `App.js`: Main React component for the application.
  - `index.js`: Entry point for the React application.

## Future Improvements 🛠️

While the current version of the Simple Bank application provides basic functionality, there are several potential improvements that can be made:

- **Enhanced Security**: Implement additional security features such as multi-factor authentication and role-based access control.
- **User Interface**: Improve the user interface to provide a more intuitive and user-friendly experience.
- **Additional Features**: Add more features such as transaction history, account statements, and notifications for transactions.
- **Smart Contract Optimization**: Optimize the smart contract for gas efficiency

 and performance.

## Contributing 🤝

Contributions are welcome! If you have any ideas, suggestions, or bug reports, please open an issue or submit a pull request. Follow these steps to contribute:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes with descriptive messages.
4. Push your changes to your forked repository.
5. Open a pull request to the main repository.

## License 📄

This project is licensed under the MIT License. See the LICENSE file for details.

## Thank You

Thank you for using Simple Bank! If you have any questions or need further assistance, feel free to reach out.
