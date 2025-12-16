# IonBeacon

Built for Base

IonBeacon is a lightweight Base-focused repository created to exercise wallet connectivity, Base-aware chain selection, and read-only onchain queries using official Coinbase tooling.

The project intentionally keeps scope narrow: it does not introduce custom smart contract logic, but instead validates infrastructure, RPC access, and explorer visibility on Base networks.

## Quick Context

IonBeacon targets the Base ecosystem directly and references:
- Base Mainnet (chainId 8453)
- Base Sepolia testnet (chainId 84532)
- Basescan explorers for deployment and verification workflows

## Networks

Base Sepolia (Testnet)
- chainId (decimal): 84532
- Explorer: https://sepolia.basescan.org
- Public RPC: https://sepolia.base.org

Base Mainnet
- chainId (decimal): 8453
- Explorer: https://basescan.org
- Public RPC: https://mainnet.base.org

## Application Flow

Primary file: app/ionBeacon.ts

When running the application:
- An OnchainKit provider is initialized for the selected Base network
- Wallet connection UI is rendered via OnchainKit Wallet
- A Viem public client is pinned to Base RPC
- The app retrieves:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a supplied address
- Explorer links are surfaced for manual inspection on Basescan

## Repository Layout

- app/
  - ionBeacon.ts
    React entry point combining OnchainKit wallet UX with Viem-based Base RPC reads.

Supporting files typically included in the repository:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env (optional, not committed)

## Tooling & Libraries

- OnchainKit  
  Wallet UX components and Base-first primitives  
  https://github.com/coinbase/onchainkit

- Viem  
  JSON-RPC client used for Base chain reads

## Setup & Installation

Requirements:
- Node.js 18 or newer
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project with a standard React/Vite or Next.js dev server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Usage Notes

- Base Sepolia is recommended for testing and validation
- If RPC chainId does not match the selected network, verify wallet network settings
- Public RPC endpoints are rate-limited and intended for development use

## Base Mainnet Deployment

Deployed on Base Mainnet

Network: Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Deployed contract address:  
your_adress  

Basescan deployment and verification links:
- Contract address:  
  https://basescan.org/address/your_adress  
- Contract verification (source code):  
  https://basescan.org/address/your_adress#code  

## License

MIT License

## Author

GitHub: https://github.com/your-handle  
Public contact (email): your-name@proton.me  
Public contact (X): https://x.com/your-handle  

## Testnet Deployment (Base Sepolia)

To validate Base compatibility prior to mainnet usage, one or more contracts may be deployed on the Base Sepolia test network.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code  

Contract #2 address (optional):  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code  

Contract #3 address (optional):  
your_adress  

Deployment and verification:
- https://sepolia.basescan.org/address/your_adress  
- https://sepolia.basescan.org/your_adress/0#code  

These testnet deployments are used to confirm Base tooling compatibility, account abstraction–related workflows, and onchain read behavior in a controlled environment before production usage.
