# 🤞xHolas [deployment](xholas.vercel.app) | [slides](https://docs.google.com/presentation/d/1V0T_K-vqmEk2MqcLvSJt26at3LBLFKhMuJ7ZT80KZeU/edit?usp=sharing)

<img src="https://github.com/xHolas-Pit/.github/blob/main/profile/batmanMeme.png?raw=true" width=250>
<!-- <img src="https://github.com/xHolas-Pit/.github/blob/main/profile/distractedMeme.jpg?raw=true" width=350> -->

## Problem 

There are numerous defi strategies in the world of interoperable blockchains, but implementing on-chain executions in solidity is difficult. As defi grows, non-technical traders should have the tools to deploy custom strategies without writing code. 

## Solution 

So we built xHolas, a plug-and-play defi strategy builder, to provide a no-code tool for executing cross-chain defi strategies with the following properties: 
* batch execution: any number of txs should be executed with one signature
* cross chain: swaps/lending/borrowing/etc. should be executed across multiple chains within a single batch execution   

### Smart Contract Architecture
<img src="https://github.com/xHolas-Pit/.github/blob/main/profile/xHolasDiagram.png?raw=true" width=250>
1. the frontend app receives user payload, aka a list of transactions they want to perform along with their parameters. 
  * ex) swap 25 $ETH to $USDC on Ethereum -> bridge output $USDC to Solana -> swap output $USDC to $WETH -> bridge $WETH back to $ETH Ethereum 
2. the xHolas contract executes transactions in a loop through delegate calls
3. each call gets routed to a handler contract based on the corresponding strategy (swap, bridge, borrow, lend), and for cross-chain txs, the remaining tx function names and parameters are encoded and sent over to the target chain as a Wormhole VAA payload to be executed at the target chain's receiving contract. 

Feel free to check out the current [deployment](xholas.vercel.app) and our presentation [slides](https://docs.google.com/presentation/d/1V0T_K-vqmEk2MqcLvSJt26at3LBLFKhMuJ7ZT80KZeU/edit?usp=sharing)

💸 This project won a $10K bounty at [xHack](https://jumpcrypto.com/xhack/) hosted by Jump Crypto!

⚠️ The webapp and the contracts were created at a hackathon and might not be fully functional at the time of use. The project is not being actively maintained and is opensourced as an educational resource. 

## Resources for Cross-Chain Development 

We learned a lot about wormhole's infrastructure, and for anyone hoping to add cross chain functionalities to their dapp using wormhole, we compiled the following resources: 
- 
