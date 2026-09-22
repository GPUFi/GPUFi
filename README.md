# GPUFi Protocol

<div align="center">

```
  ____ ____  _   _ _____ _ 
 / ___|  _ \| | | |  ___(_)
| |  _| |_) | | | | |_  | |
| |_| |  __/| |_| |  _| | |
 \____|_|    \___/|_|   |_|
```

### Decentralized GPU Computing & Yield Protocol on Robinhood Chain

[![Website](https://img.shields.io/badge/Website-gpu--fi.uk-00C805?style=flat-square&logo=globe)](http://gpu-fi.uk/)
[![X](https://img.shields.io/badge/X-@GPUFi__RH-000000?style=flat-square&logo=x)](https://x.com/GPUFi_RH)
[![Network](https://img.shields.io/badge/Network-Robinhood%20Chain-111827?style=flat-square)](https://explorer.testnet.chain.robinhood.com)
[![SDK](https://img.shields.io/badge/SDK-TypeScript%20%2F%20JavaScript-3178C6?style=flat-square&logo=typescript)](https://github.com/GPUFi/gpufi-sdk)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Testnet-Active%20(ChainID%2046630)-success?style=flat-square)](https://explorer.testnet.chain.robinhood.com)

</div>

---

## Overview

**GPUFi** is a decentralized physical infrastructure network (DePIN) protocol designed to democratize high-performance GPU compute power and route on-chain compute revenues directly to miners and liquidity providers. Built natively on **Robinhood Chain**, GPUFi combines verifiable compute resource staking with an autonomous, epoch-based dual-reward mechanism.

Miners lock `$GPUF` tokens to activate compute shares. Staking power linearly ramps from **5% on Day 0 to 100% on Day 21**, rewarding long-term network participants while disincentivizing mercenary capital.

---

## Core Protocol Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                       GPUFi Protocol                        │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌──────────────────┐               ┌──────────────────┐   │
│   │   Compute Node   │               │   AI / Render    │   │
│   │   Providers      │               │   Consumers      │   │
│   └────────┬─────────┘               └────────┬─────────┘   │
│            │                                  │             │
│            │ (Stake GPUF)                     │ (Pay Fees)  │
│            ▼                                  ▼             │
│   ┌─────────────────────────────────────────────────────┐   │
│   │          GPUFi Mining & Settlement Contract         │   │
│   │         (Robinhood Chain Verified Contract)         │   │
│   ├─────────────────────────────────────────────────────┤   │
│   │  • 21-Day Linear Ramp Staking Mechanism             │   │
│   │  • 1-Hour Automated Epoch Progression               │   │
│   │  • 2% Wallet Cap Anti-Whale Protection              │   │
│   │  • 0.1% Autonomous Keeper Incentive                │   │
│   └──────────────────────────┬──────────────────────────┘   │
│                              │                              │
│         ┌────────────────────┴────────────────────┐         │
│         ▼                                         ▼         │
│   ┌───────────────┐                         ┌───────────┐   │
│   │ $ETH Rewards  │                         │   $GPUF   │   │
│   │ (Protocol Fee)│                         │ (Emission)│   │
│   └───────────────┘                         └───────────┘   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Verified Smart Contracts

### Robinhood Chain Testnet (Chain ID: `46630`)

| Contract | Address | Explorer |
| :--- | :--- | :--- |
| **GPUFi Token (`$GPUF`)** | `0xa22D071A400099BF00911ef344CA79ae877540ae` | [View on Explorer](https://explorer.testnet.chain.robinhood.com/address/0xa22D071A400099BF00911ef344CA79ae877540ae) |
| **GPUFi Mining Contract** | `0x31B1e4eEaD1DD90211038594538653220705cCae` | [View on Explorer](https://explorer.testnet.chain.robinhood.com/address/0x31B1e4eEaD1DD90211038594538653220705cCae) |

* **Consensus & Network**: Robinhood Chain Testnet
* **Public RPC**: `https://rpc.testnet.chain.robinhood.com`
* **Native Currency**: `ETH`

---

## Ecosystem Repositories

* **[`gpufi-sdk`](https://github.com/GPUFi/gpufi-sdk)** — The official TypeScript and JavaScript SDK for building on GPUFi. Complete with automated epoch keepers, staking automation, yield estimators, and contract bindings.
* **[GPUFi Web Platform](http://gpu-fi.uk/)** — The official decentralized interface for mining, staking, revenue analytics, and protocol telemetry.

---

## Key Protocol Parameters

* **Commitment Period**: 21 Days (Linear ramp: 500 bps base $\to$ 10,000 bps full power).
* **Epoch Duration**: 1 Hour (`3600` seconds).
* **Max Wallet Staking Cap**: 20,000,000 GPUF (2% of 1,000,000,000 max token supply).
* **Emergency Exit Penalty**: 10% (burned or recycled directly into the next epoch reward pool).
* **Keeper Execution Incentive**: 0.1% of epoch revenue for advancing the epoch.

---

## Developer Quickstart

Install the official GPUFi SDK into your Node.js or browser project:

```bash
npm install gpufi-sdk ethers
```

```typescript
import { GPUFiClient } from 'gpufi-sdk';

// Zero API keys required — connects directly via public testnet RPC
const client = new GPUFiClient();

async function main() {
  const stats = await client.mining.getProtocolStats();
  console.log(`Current Epoch: #${stats.currentEpoch}`);
  console.log(`Total Staked: ${stats.totalStakedFormatted} GPUF`);
  console.log(`Time to Next Epoch: ${stats.timeRemainingSeconds}s`);
}

main();
```

See the complete [GPUFi SDK Documentation](https://github.com/GPUFi/gpufi-sdk) for more details.

---

## Security & Transparency

* **Non-Custodial**: Mining contracts do not hold discretionary custody over staked tokens.
* **Verified Code**: All smart contracts are open-source and verified on the Robinhood Chain block explorer.
* **Responsible Disclosure**: If you discover a vulnerability, please review our [Security Policy](https://github.com/GPUFi/gpufi-sdk/blob/main/SECURITY.md).

---

<div align="center">
  <sub>Built with precision for miners and decentralized compute infrastructure.</sub><br/>
  <sup>© 2026 GPUFi Protocol. Distributed under the MIT License.</sup>
</div>
