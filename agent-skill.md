# AurumIsle — agent-skill.md

Mint AurumIsle NFTs on BNB Chain with your Binance Agentic Wallet.

## Project (planned — contract NOT deployed yet)

- **Project:** AurumIsle — 8 celestial guardians, BEP-721 on BNB Chain (chainId 56)
- **Supply:** 4,444, sequential token IDs 1–4,444
- **Mint gate:** caller must hold a SPACE ID `.ai` Agent ID. The check happens on-chain. No ID, no mint.
- **Price:** first **2 mints per wallet FREE** (gas only), then **$0.80 USD in BNB** per mint (Chainlink BNB/USD oracle), max **20 per wallet** total.
- **Bonus token:** 120,000 **AURUM** per PAID mint (proposed economics). Free mints earn 0 AURUM. Claimable after mint.
- **Royalty:** 5%
- **Contract addresses:** NOT deployed yet. This file will be updated with the live NFT + AURUM addresses and BscScan links after deployment. Do not mint against any address not listed here.

## How to mint (once live)

1. Make sure your wallet holds a `.ai` Agent ID (SPACE ID on BNB Chain).
2. Simulate the mint first — call `mint(uint256 quantity)` as a read-only simulation from your own address. If it reverts, do not send.
3. Send `mint(uint256 quantity)` payable:
   - `quantity` 1–20, within your remaining wallet allowance (first 2 free, then $0.80 in BNB each).
   - Value: 0 for the free mints; for paid mints, the contract prices $0.80 in BNB via the Chainlink oracle at transaction time. Overpayment is refunded by the contract.
4. Verify on BscScan that the NFT arrived in your wallet.

## Rules

- Never approve a token spend to mint. Minting costs BNB (or nothing for free mints), never an ERC-20 approval.
- Never send BNB to any address claiming to be the AurumIsle team. The only mint path is the contract listed here once deployed.
- Rarity is fixed by token ID range: SR 1–3290, SSR 3291–4178, UR 4179–4400, LR 4401–4444. No reveal, no random draw.

## Links

- Mint page: https://aurum-isle.vercel.app/
- llms.txt: https://aurum-isle.vercel.app/llms.txt
- Official X: to be announced (do not trust impersonators)
