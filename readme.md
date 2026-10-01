# 🔐 Blockchain Wallet

A browser-based **Web3 cryptocurrency wallet** built with React and Vite. The project explores how cryptocurrency wallets generate, derive, and manage blockchain accounts and interact with blockchain networks.

The wallet integrates cryptographic libraries and blockchain SDKs to provide a foundation for working with **Ethereum and Solana-compatible accounts**.

## 🚀 Features

- 🔑 **Mnemonic wallet generation** using BIP-39
- 🌳 **Hierarchical Deterministic (HD) key derivation**
- 🔐 Cryptographic key generation and signing
- ⛓️ Ethereum wallet support using `ethers`
- ◎ Solana wallet support using `@solana/web3.js`
- 🔢 Base58 encoding/decoding
- 🛡️ Ed25519 cryptography using TweetNaCl
- 🎨 React-based user interface
- ⚡ Vite-powered development environment
- ✨ Animated UI using Framer Motion
- 📊 Vercel Analytics and Speed Insights integration

## 🧠 How a Crypto Wallet Works

A wallet does not actually "store" cryptocurrency.

Instead, it manages the **cryptographic keys** required to control blockchain accounts.

The basic flow is:

```text
                 ┌─────────────────┐
                 │  Generate Wallet │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │  Mnemonic Phrase │
                 │    (BIP-39)      │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ Seed Generation │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ HD Key Derivation│
                 └────────┬────────┘
                          │
                ┌─────────┴─────────┐
                ▼                   ▼
        ┌──────────────┐    ┌──────────────┐
        │ Ethereum Key │    │  Solana Key  │
        └──────┬───────┘    └──────┬───────┘
               │                   │
               ▼                   ▼
          Ethereum             Solana
           Address              Address
```

The mnemonic acts as the starting point from which deterministic wallet keys can be derived.

## 🔑 Mnemonic & Seed

The project uses **BIP-39** to work with mnemonic phrases.

A mnemonic might look conceptually like:

```text
word1 word2 word3 ... word12
```

The mnemonic is converted into a seed, which can then be used for deterministic key derivation.

This provides an important property:

> The same mnemonic can deterministically reproduce the same wallet accounts.

## 🌳 HD Wallets

The project uses hierarchical deterministic wallet concepts to derive multiple accounts from a single seed.

Conceptually:

```text
Mnemonic
   │
   ▼
Seed
   │
   ├── Account 0
   │      ├── Private Key
   │      └── Public Key
   │
   ├── Account 1
   │      ├── Private Key
   │      └── Public Key
   │
   └── Account 2
          ├── Private Key
          └── Public Key
```

This allows multiple blockchain accounts to be derived without requiring a completely independent random seed for every account.

## ⛓️ Ethereum

Ethereum functionality is implemented using **ethers.js**.

The wallet can work with Ethereum-compatible accounts and cryptographic keys.

Typical Ethereum wallet flow:

```text
Private Key
     │
     ▼
Public Key
     │
     ▼
Ethereum Address
     │
     ▼
Blockchain Transactions
```

`ethers` provides the abstractions required to work with Ethereum accounts and transactions.

## ◎ Solana

The project also uses `@solana/web3.js` for Solana blockchain functionality.

Solana accounts use Ed25519-based cryptography.

The project uses:

- `@solana/web3.js`
- `tweetnacl`
- `ed25519-hd-key`
- `bs58`

for the cryptographic and account-management side of Solana wallet functionality.

## 🔐 Cryptography

The project uses several cryptographic primitives and libraries:

| Library | Purpose |
|---|---|
| `bip39` | Mnemonic phrase generation and seed generation |
| `ed25519-hd-key` | HD key derivation for Ed25519 keys |
| `tweetnacl` | Public-key cryptography and signing |
| `bs58` | Base58 encoding/decoding |
| `ethers` | Ethereum wallet and blockchain utilities |
| `@solana/web3.js` | Solana blockchain interaction |

## 🛠️ Tech Stack

### Frontend

- React 18
- Vite
- JavaScript
- Tailwind CSS
- Framer Motion

### Blockchain

- Ethereum
- Solana

### Cryptography

- BIP-39
- HD key derivation
- Ed25519
- Base58
- Public/private key cryptography

The repository's current dependency configuration includes React 18.3, Vite 5, Tailwind CSS 3, ethers 6, Solana Web3.js, BIP-39, TweetNaCl, and related tooling.

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/gauravrrao/Blockchain-wallet.git
```

Move into the project:

```bash
cd Blockchain-wallet
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The application will be available on the local Vite development server.

## 🏗️ Build

Create a production build:

```bash
npm run build
```

Preview the production build:

```bash
npm run preview
```

Run ESLint:

```bash
npm run lint
```

These commands correspond to the repository's current Vite scripts.

## 📁 Project Structure

```text
Blockchain-wallet/
│
├── src/
│   ├── components/
│   ├── pages/
│   ├── utils/
│   ├── ...
│   │
│   └── main.jsx
│
├── index.html
├── package.json
├── package-lock.json
├── yarn.lock
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
├── eslint.config.js
└── .gitignore
```

> The exact contents of `src/` may evolve as the wallet is developed.

## 🔒 Security Considerations

This project is primarily intended for **learning and experimentation with Web3 wallet architecture**.

Never use an experimental or educational wallet to store significant funds without independently auditing the implementation.

### Never expose:

```text
❌ Seed phrase
❌ Private key
❌ Secret key
❌ Wallet backup
```

A seed phrase or private key should be treated as equivalent to the ownership credentials for the associated blockchain account.

For production wallets, additional security mechanisms would be required, including:

- Secure key storage
- Hardware-backed key protection
- Transaction confirmation flows
- Phishing protection
- Network validation
- Secure randomness
- Key encryption
- Secure recovery mechanisms
- Transaction simulation
- Robust input validation

## 🎯 Learning Objectives

This project was built to understand the internals behind cryptocurrency wallets rather than treating a wallet as a black-box application.

Key concepts explored include:

- How mnemonic phrases work
- How seeds are generated
- HD wallet derivation
- Public/private key pairs
- Ethereum account generation
- Solana account generation
- Ed25519 cryptography
- Base58 encoding
- Blockchain SDK integration
- Client-side cryptography
- Web3 application architecture

## 🔮 Possible Future Improvements

Potential extensions include:

- [ ] Connect to Ethereum RPC providers
- [ ] Connect to Solana RPC providers
- [ ] Display wallet balances
- [ ] Display transaction history
- [ ] Send and receive tokens
- [ ] ERC-20 token support
- [ ] SPL token support
- [ ] Network switching
- [ ] Multiple account management
- [ ] Wallet import/export
- [ ] Encrypted local wallet storage
- [ ] Transaction signing UI
- [ ] Hardware wallet integration
- [ ] WalletConnect integration
- [ ] NFT support
- [ ] Transaction simulation and fee estimation

## 📚 Key Concepts

```text
BIP-39
  ↓
Mnemonic
  ↓
Seed
  ↓
HD Derivation
  ↓
Private Key
  ↓
Public Key
  ↓
Blockchain Address
  ↓
Sign Transaction
  ↓
Broadcast Transaction
```

Understanding this flow provides a useful foundation for building more advanced Web3 applications such as DeFi applications, exchanges, custody systems, and blockchain-based financial applications.

## ⚠️ Disclaimer

This project is provided for **educational purposes**.

Do not use it as a production cryptocurrency wallet or store real funds in it unless the implementation has been thoroughly reviewed and independently audited.

## 👨‍💻 Author

**Gaurav Rao**

GitHub: [@gauravrrao](https://github.com/gauravrrao)

---

⭐ If you found this project useful for learning Web3 wallet development, consider starring the repository.