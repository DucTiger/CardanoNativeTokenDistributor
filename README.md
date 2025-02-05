# Cardano Native Token Distributor

This module provides a way to distribute native tokens on the Cardano blockchain in a manner similar to how staking rewards are distributed. It aims to minimize the number of UTXOs created and reduce transaction fees for token holders.

## Features

* **Periodic Distribution:** Tokens are automatically distributed to designated wallets at set intervals (e.g., every epoch).
* **UTXO Consolidation:** Instead of creating a new UTXO for each wallet in each distribution, tokens for an entire epoch are held within a single UTXO. This reduces network load and storage requirements.
* **Claim Mechanism:** Token holders can claim their accumulated tokens from the distribution UTXO at any time.
* **Batching:** Claim transactions can be batched together to further reduce transaction fees.
* **Customizable:** The distribution logic (e.g., how much each wallet receives) can be customized via a smart contract.

## How It Works

1. **Initialization:**
   * A smart contract is deployed to the Cardano blockchain.
   * The total amount of tokens to be distributed is deposited into the contract.

2. **Distribution:**
   * At the start of each epoch, the smart contract calculates the distribution for each wallet based on the defined logic.
   * A single UTXO is created, containing the tokens for that epoch's distribution. The contract stores a record of how much each wallet is owed.

3. **Claiming:**
   * Token holders can submit a transaction to the smart contract to claim their portion of the tokens from the distribution UTXO.
   * The contract verifies the claim and transfers the appropriate amount of tokens to the holder's wallet.

4. **Batching:**
   * Multiple claim transactions can be bundled into a single transaction to reduce fees.

## Getting Started

### Prerequisites

* Basic understanding of Cardano and native tokens.
* Familiarity with Cardano smart contract development (Plutus or Marlowe).
* Cardano CLI or other tools for interacting with the Cardano blockchain.

### Installation

1. Clone the repository: `git clone https://github.com/DucTiger/CardanoNativeTokenDistributor.git`
2. Install dependencies (if any).
3. Deploy the smart contract to the Cardano blockchain.

### Usage

1. Configure the distribution logic within the smart contract.
2. Deposit the tokens to be distributed into the contract.
3. (Optional) Set up a process to automatically trigger the distribution at the start of each epoch.
4. Token holders can then use a Cardano wallet or other tool to claim their tokens from the contract.

## Examples

* Provide examples of how to interact with the smart contract using the Cardano CLI or other tools.
* Show how to customize the distribution logic.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

MIT

## Contact

* Duc Tiger
* duc.tigerpool@gmail.com
