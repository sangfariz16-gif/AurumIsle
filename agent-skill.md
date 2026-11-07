# AurumIsle — agent-skill.md

Mint AurumIsle NFTs on BNB Chain with your Binance Agentic Wallet.

## Project (planned — contract NOT deployed yet)

- **Project:** AurumIsle — a floating isle of gold, BEP-721 on BNB Chain (chainId 56)
- **Supply:** 1,111, token IDs drawn at RANDOM (on-chain swap-and-pop, pseudo-random — NOT Chainlink VRF). Any mint can land any tier.
- **Mint gate:** caller must hold a SPACE ID `.ai` Agent ID. The check happens on-chain. No ID, no mint.
- **Price:** first **1 mint per wallet FREE** (gas only), then a flat **0.0003 BNB** per mint, max **11 per wallet** total (1 free + 10 paid).
- **Bonus token:** 120,000 **AURUM** per PAID mint. Free mints earn 0 AURUM. Claimable after mint.
- **Royalty:** 5%
- **Contract addresses:** NOT deployed yet. Predicted addresses: NFT `0xC52a979C20C5a43e5Be4Ffa6d1A4DD50069D5E2D`, AURUM token `0x1478422c8a2A38f0516538F07cE3cDD762582c42` — these will be verified on-chain at deploy. Do not mint against any address not listed here.

## How to mint (once live)

1. Make sure your wallet holds a `.ai` Agent ID (SPACE ID on BNB Chain).
2. Simulate the mint first — call `mint(uint256 quantity)` as a read-only simulation from your own address. If it reverts, do not send.
3. Send `mint(uint256 quantity)` payable:
   - `quantity` 1–11, within your remaining wallet allowance (first 1 free, then 0.0003 BNB each).
   - Value: 0 for the free mint; for paid mints, 0.0003 BNB each — get the exact quote from `quoteFor(wallet, qty)` first. Overpayment is refunded by the contract.
4. Verify on BscScan that the NFT arrived in your wallet. Your token ID is drawn at random — check its tier from the metadata.

## Rules

- Never approve a token spend to mint. Minting costs BNB (or nothing for the free mint), never an ERC-20 approval.
- Never send BNB to any address claiming to be the AurumIsle team. The only mint path is the contract listed here once deployed.
- Rarity is fixed by token ID range: Gilded 1–555 (Golden Pine Ridge), Radiant 556–833 (Silk Wave Bay), Celestial 834–999 (Celestial Ring Peak), Divine 1000–1088 (Gilded Waterfall), Eternal 1089–1111 (The Golden Summit). Each tier has its own artwork. No reveal — the ID (and tier) is drawn at mint time.

## Links

- Mint page: https://aurum-isle.vercel.app/
- llms.txt: https://aurum-isle.vercel.app/llms.txt
- Official X: to be announced (do not trust impersonators)
