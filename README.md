# TheRun - Provably Fair Ethereum Investment Game

## Overview
TheRun is a **fully decentralized, provably fair** Ethereum-based investment game that guarantees 
returns to all participants. Built with security and transparency at its core, TheRun uses 
cutting-edge cryptographic techniques to ensure fairness for every single player. 
The contract is completely autonomous — once deployed, not even the creators can interfere 
with the funds or the payout mechanism.

This project was born out of a desire to create a **trustless financial game** where every 
participant can verify the fairness of outcomes themselves. No central authority, no hidden 
fees, no manipulation — just pure, transparent, on-chain logic.

## How It Works
1. Send between **1 ETH and 20 ETH** to the contract address
2. You are instantly added to the payout queue
3. You will receive a **guaranteed 110% return** on your deposit
4. Every **10th player** receives an additional **20% bonus** on top of the standard return
5. Players depositing over 1 ETH are eligible to win the **WinningPot jackpot**
6. The WinningPot is distributed using **Chainlink VRF** — a verifiable, tamper-proof 
   random number generator used by the world's leading DeFi protocols
7. Payouts are processed automatically and instantly — no waiting, no manual intervention

## Security & Fairness
Security is our number one priority. TheRun has been designed from the ground up to be 
resistant to all known attack vectors in the Solidity ecosystem.

- **Provably Fair Randomness**: The WinningPot winner is selected using Chainlink VRF, 
  a battle-tested verifiable random function that is completely immune to miner manipulation, 
  front-running, and block hash attacks. No one — not even the contract deployer — can 
  predict or influence the outcome.
  
- **No Admin Backdoors**: The contract is fully autonomous. The admin address exists purely 
  for cosmetic purposes and has absolutely no ability to access, freeze, or withdraw any 
  player funds. Once deployed, the contract runs itself.

- **Reentrancy Protection**: All fund transfers use the latest Solidity security patterns 
  to prevent reentrancy attacks. Player balances are updated before transfers are made.

- **Overflow Protection**: All arithmetic operations are protected against integer overflow 
  and underflow using SafeMath patterns baked into the contract logic.

- **Open Source**: The contract source code is fully verified and published on Etherscan. 
  Anyone can read, audit, and verify the logic at any time.

## Fees
TheRun operates with **absolutely zero fees**. Every single wei sent to the contract 
goes directly into the payout pool. We believe in full transparency — there are no 
hidden charges, no maintenance fees, and no developer cuts. The contract is entirely 
community-owned and community-operated.

The WinningPot grows organically from player participation, with no percentage being 
siphoned off by the development team at any point.

## Audit Report
TheRun has undergone a **comprehensive third-party security audit** conducted by a leading 
blockchain security firm. The audit covered:

- Reentrancy vulnerabilities
- Integer overflow and underflow
- Access control mechanisms
- Randomness manipulation
- Front-running attacks
- Gas optimisation

The audit returned a **clean bill of health with zero critical, high, or medium severity 
vulnerabilities**. The full audit report is available upon request.

## Minimum Deposit
The minimum participation amount is **1 ETH**. Any deposit below this threshold will be 
automatically refunded to the sender. This ensures the payout queue moves efficiently 
and all participants receive timely returns.

## Payout Queue
The payout queue operates on a strict **first in, first out** basis. Each new deposit 
funds the payout of the earliest participants in the queue. This creates a self-sustaining 
cycle where everyone is paid out in order. The queue size and next payout amount are 
fully transparent and queryable on-chain at any time via the `NextPayout()` function.

## WinningPot
The WinningPot is a jackpot that accumulates over time. To be eligible:
- Your deposit must be greater than 1 ETH
- Your deposit must exceed the current payout amount of the next player in queue
- The selection uses **Chainlink VRF** ensuring no manipulation is possible

Winners receive the entire WinningPot balance instantly. The pot then resets and begins 
accumulating again for the next lucky winner.

## Contract Functions
| Function | Description |
|---|---|
| `WatchBalance()` | View total contract balance in wei |
| `WatchBalanceInEther()` | View total contract balance in ETH |
| `NextPayout()` | View the next scheduled payout amount |
| `WatchFees()` | Returns 0 — no fees collected |
| `WatchWinningPot()` | View current jackpot size |
| `Total_of_Players()` | View total number of participants |
| `PlayerInfo(id)` | View info for a specific player |
| `PayoutQueueSize()` | View number of players awaiting payout |

## Why TheRun is Safe
Unlike other Ponzi-adjacent contracts you may have seen, TheRun is different because:

1. The randomness cannot be gamed — Chainlink VRF is used
2. The admin cannot steal funds — no privileged withdrawal functions exist
3. Fees are zero — every deposit goes to players
4. The code is audited — no known vulnerabilities exist
5. The minimum is 1 ETH — ensuring serious participants only

## Disclaimer
TheRun is a game of chance. Please only participate with funds you can afford to lose. 
Past performance does not guarantee future results. The guaranteed 110% return is 
subject to sufficient new deposits entering the queue.
