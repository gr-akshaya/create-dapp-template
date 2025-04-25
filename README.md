# Core Blockchain Quickstart (Next.js + RainbowKit)

A lightweight starter kit to build dApps on the **Core Blockchain**, using **Next.js** and **RainbowKit** for seamless wallet connectivity

## ✨ Features

- Built with **Next.js 15**
- **RainbowKit** for wallet connection
- **wagmi** + **viem** for Core-compatible blockchain interaction
- **React Toastify** for notifications
- Pre-configured for **Core Mainnet** and **Core Testnet**

## 📦 Tech Stack

- [Next.js](https://nextjs.org/)
- [RainbowKit](https://rainbowkit.com/)
- [wagmi ](https://wagmi.sh/)
- [viem 2.27.2](https://viem.sh/)
- [Core Official Documentation](https://docs.coredao.org/)

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-org/core-quickstart.git
cd core-quickstart
```

### 2. Install dependencies

```bash
npm install
# or
yarn install
```

### 3. Configure your project

Create a `.env.local` file in the root directory and add your project ID:

```bash
NEXT_PUBLIC_WALLETCONNECT_PROJECT_ID=your_project_id_here
```

## Project Structure

```
core-quickstart/
├── src/
│   ├── pages/         # Next.js pages
│   ├── styles/        # CSS styles
│   └── wagmi.ts       # Wallet configuration
├── public/            # Static assets
└── package.json       # Project dependencies
```

## Wallet Setup with RainbowKit

```ts
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

## Development

```bash
npm run dev     # Start dev server
npm run build   # Build for production
npm run start   # Run production server
```

## Example: Home Page

```tsx
// pages/index.tsx
import { ConnectButton } from "@rainbow-me/rainbowkit";
import styles from "../styles/Home.module.css";

export default function Home() {
  return (
    <div className={styles.container}>
      <h1>🚀 Welcome to Core dApp Starter</h1>
      <ConnectButton />
    </div>
  );
}
```
