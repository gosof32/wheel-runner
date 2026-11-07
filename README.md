# 🐹 Wheel Runner

An endless runner powered by **Squeektoshi**, the hamster whose wheel runs [Squeekchain](https://squeekchain.com).

You run on the same wheel he does. The game reads Squeekchain's public API every 15 seconds and the real hamster changes how the game plays:

| Squeekchain signal | What happens in the game |
| --- | --- |
| Wheel **RPM** (`/v1/status`) | Sets your running speed and your score multiplier (faster hamster = harder run, bigger score) |
| Wheel **stopped / sleeping** | Night Mode: the world goes dark, night owls appear, seeds are worth x2 |
| **New Squeek block** mined | A Golden Wheel spawns: grab it for a 6-second shield |
| Hamster state at the end of your run | Call "Running" or "Sleeping" before you start; a correct call adds +50% to your score |

The big wheel in the background spins at Squeektoshi's actual RPM.

## Wallet (Sepolia)

- **Connect Wallet** (MetaMask or any EIP-1193 wallet) switches you to Ethereum Sepolia (chainId 11155111), adding the network if needed, and shows your address and Sepolia ETH balance.
- After a run, **Sign score** signs a message with your score, seeds, the Squeek block and the wheel state at the finish (`personal_sign`, no gas, no transaction). Signed runs are listed per wallet.
- On a phone without a wallet browser, Connect opens the game inside the MetaMask app.

## Play

Open `index.html` in any browser, or play the hosted version via GitHub Pages.

- **Tap / Space / ↑**: jump (tap again in the air to double-jump)
- Collect 🌻 seeds, dodge mousetraps, boxes, cats and owls
- Best score is saved in your browser

If the Squeekchain API can't be reached from your browser, the game falls back to simulated wheel data and says so on the start screen.

## Tech

Single static `index.html`, plain JavaScript and Canvas with a dot-matrix renderer, no build step, no dependencies. Wallet is optional and never sends a transaction. Free to play.

## Squeekchain Genesis

Built for the Squeekchain Genesis code lane.
