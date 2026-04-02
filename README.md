# WMON — Wrapped Monad

A minimal, single-file dApp for wrapping and unwrapping MON ↔ WMON on Monad Mainnet.

## Live

Deploy `index.html` anywhere — Cloudflare Workers, Vercel, Netlify, GitHub Pages, or any static host.

## What it does

- **Wrap** — Send MON to the WMON contract, receive WMON 1:1
- **Unwrap** — Burn WMON, receive MON 1:1, no fee
- **Live stats** — Total WMON supply and your balance, auto-refreshed every 8s
- **Wallet** — MetaMask (or any EIP-1193 wallet). Automatically prompts to add/switch to Monad Mainnet

## Contract

| | |
|---|---|
| **Address** | `0x2cE8C8F4961a54B2e87585f4178467006B76B418` |
| **Network** | Monad Mainnet |
| **Chain ID** | 143 (`0x8f`) |
| **Explorer** | [monadscan.com](https://monadscan.com/address/0x2cE8C8F4961a54B2e87585f4178467006B76B418) |

## Stack

- Vanilla HTML / CSS / JS — zero build step, zero dependencies to install
- [ethers.js v6](https://docs.ethers.org/v6/) via CDN
- RPC endpoints: `monad-mainnet.drpc.org`, `rpc.monad.xyz`

## Deploy

### Cloudflare Workers (static)
Upload `index.html` as a Worker asset or use Pages.

### Vercel / Netlify
Drop `index.html` into a repo and connect. No config needed.

### GitHub Pages
Push `index.html` to the `gh-pages` branch or `/docs` folder and enable Pages in repo settings.

### Local
```bash
# Python
python3 -m http.server 8080

# Node
npx serve .
```

## Usage

1. Open the app in a browser with MetaMask installed
2. Click **Connect Wallet** — the app will prompt to add Monad Mainnet if not already in your wallet
3. **Wrap tab** — enter an amount of MON and click Wrap. MAX reserves 0.01 MON for gas
4. **Unwrap tab** — enter an amount of WMON and click Unwrap. No fee, no slippage

## RPC / CORS notes

The app reads chain state via direct `fetch` calls to public RPC endpoints. Alchemy's demo key is excluded — it returns 429s with missing CORS headers. If you want to use a private RPC, update `READ_RPCS` in the script block.

## License

MIT
