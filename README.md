# create-dapp-template

> A lightweight, developer-friendly starter kit for building decentralized applications on the Core Blockchain. Preconfigured with Hardhat, Next.js, and RainbowKit, it streamlines your development process and gets your dApp up and running in minutes!

[![npm version](https://img.shields.io/npm/v/create-dapp-template.svg)](https://www.npmjs.com/package/create-dapp-template)
[![npm downloads](https://img.shields.io/npm/dt/create-dapp-template.svg)](https://www.npmjs.com/package/create-dapp-template)

## Features

- Built with Next.js 15
- RainbowKit for wallet connection
- wagmi + viem for blockchain interaction
- React Toastify for notifications
- Pre-configured for Core Mainnet and Core Testnet

## Quick Start

```bash
npx create-dapp-template@latest your-dapp-name
```

## Usage

```bash
# Navigate to the folder
cd your-dapp-name

# Start development server
npm run dev
# or
yarn dev
```

## Configuration

Create a `.env.local` file in the root directory:

```bash
NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id_here
PRIVETKEY=your_private_key
```

## Tech Stack

- Next.js
- RainbowKit
- wagmi
- viem
- Hardhat

## Project Structure

```
create-dapp-template/
├── artifacts/           # Hardhat compiled contract artifacts
├── cache/              # Hardhat cache
├── contracts/          # Smart contracts
├── scripts/            #Hardhat deployment scripts
├── src/
│   ├── pages/         # Next.js pages
│   ├── styles/        # CSS styles
│   └── wagmi.ts       # Wallet configuration
├── test/              # Test files
├── package.json       # Project dependencies
├── tsconfig.json      # TypeScript configuration
└── hardhat.config.js  # Hardhat configuration
```

## Wallet Setup

```typescript
// src/wagmi.ts
import { getDefaultConfig } from "@rainbow-me/rainbowkit";
import { coreDao, coreTestnet1, coreTestnet2 } from "wagmi/chains";

export const config = getDefaultConfig({
  appName: "Core Quickstart",
  projectId: process.env.NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID!,
  chains: [coreDao, coreTestnet1, coreTestnet2],
  ssr: true,
});
```
