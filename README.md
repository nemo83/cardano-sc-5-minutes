# Cardano Smart Contract in 5 minutes w/ helios

## Prerequisites

Things you will need before starting playing around w/ this project

1. A funded wallet in a testnet. This project uses testnet `preview` by default
2. A native asset to lock in the vault. This project is minimalistic, no minting available. Hit me on twitter @cryptojoe101 if you want some nft to play around
3. Patience
4. A decent understanding of the (e)utxo model.
5. More Patience

## Running the Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## How to bootstrap the project

1. npx create-next-app@latest cardano-sc-5-minutes
2. npm i "@hyperionbt/helios"

## Gotchas

In this paragraph a couple of snippet of code to speed up the dev.

### Accessing the Cardano object

When using TypeScript this snippet is required to make editor and compiler happy

```javascript
declare global {
  interface Window {
    cardano: any;
  }
}
```

### Fetching the Network Params

Cardano Network parameters are required when finalising the transaction (eg fees, collateral etc.). 

```javascript
fetch('https://d1t0d7c2nekuk0.cloudfront.net/preview.json')
    .then(response => response.json())
    .then(params => setNetworkParams(new NetworkParams(params)))
```
