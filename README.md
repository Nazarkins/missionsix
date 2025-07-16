Neon bootcamp week 6
Solana Native SDK: Approving and Transferring USDC Without MetaMask
This repository contains the scripts and configuration for Week 6 of Neon Dev Bootcamp. The goal was to explore how Solana wallets like Phantom can interact directly with Neon EVM dApps, bypassing MetaMask entirely, using the Solana Native SDK.

!! What We Did
Configured the development environment with access to Neon Devnet and Solana Devnet.

Funded our Solana wallet with DEVNET SOL to pay for transaction fees.

Used Solana Native SDK to initialize a Solana wallet and link it to a Neon EVM account.

Tested two core use cases:

Approving USDC tokens from a Solana wallet for use in Neon contracts.

Transferring USDC from Solana to a Neon EVM wallet.

!! Key Observations
Initialization: The SDK successfully mapped our Solana public key to a Neon wallet address, making it possible to interact with ERC-20 contracts on Neon directly.

Approve Script:

Checked and updated USDC allowances from Solana.

Scheduled and signed an approval transaction using the Solana keypair.

Confirmed allowance updates on the Neon EVM side.

Transfer Script:

Performed a USDC transfer from the linked Neon wallet to a random recipient.

Managed Associated Token Accounts (ATAs) and handled delegate approvals when needed.

Successfully observed balance updates after the transaction.

MetaMask was not required at any stage. Phantom handled signing and sending transactions seamlessly.

Gas estimates and transaction hashes were retrieved using Neon RPC.


We confirmed that the Solana Native SDK allows developers to bring Solana-native UX into EVM dApps. Both approval and transfer operations worked as expected, with Solana transactions triggering Neon EVM logic directly. This opens the door for building dApps where Solana users can interact without needing to understand or use Ethereum wallets.

This exercise gave us a clear understanding of:

Planning and scheduling Neon transactions from Solana.

Managing ERC-20 token approvals and transfers via Solana keypairs.

Using Solana tools like Phantom as the primary wallet in EVM-compatible environments.

📂 Project Structure
approve.js – Approves USDC tokens for Neon EVM using Solana Native SDK.

transfer.js – Transfers USDC between Neon wallets using Solana keys.

.env – Stores Solana private keys and RPC endpoint.