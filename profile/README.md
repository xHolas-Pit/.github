# 🤞xHolas 
## [deployment](xholas.vercel.app) | [slides](https://docs.google.com/presentation/d/1V0T_K-vqmEk2MqcLvSJt26at3LBLFKhMuJ7ZT80KZeU/edit?usp=sharing)

💸 This project won a $10K bounty at [xHack](https://jumpcrypto.com/xhack/) hosted by Jump Crypto!

⚠️ The webapp and the contracts were created at a hackathon and might not be fully functional at the time of use. The project is not being actively maintained and is opensourced as an educational resource. 

<!-- <img src="https://github.com/xHolas-Pit/.github/blob/main/profile/distractedMeme.jpg?raw=true" width=350> -->

## Problem 

<img src="https://github.com/xHolas-Pit/.github/blob/main/profile/batmanMeme.png?raw=true" width=300>

There are numerous defi strategies in the world of interoperable blockchains, but implementing on-chain executions in solidity is difficult. As defi grows, non-technical traders should have the tools to deploy custom strategies without writing code. 

## Solution 

### The Product

So we built xHolas, a plug-and-play defi strategy builder, to provide a no-code tool for executing cross-chain defi strategies with the following properties: 
* batch execution: any number of txs should be executed with one signature
* cross chain: swaps/lending/borrowing/etc. should be executed across multiple chains within a single batch execution   
* checkout the [xHolas-contract](https://github.com/xHolas-Pit/xHolas-contracts) repo for detailed smart contract architecture and deployments. 

## Resources for Cross-Chain Development 

We learned a lot about wormhole's infrastructure, and for anyone hoping to add cross chain functionalities to their dapp using wormhole, we compiled the following resources: 
* wormhole developer docs: https://book.wormhole.com
* wormhole deployed contracts: https://book.wormhole.com/reference/contracts.html
* wormhole sample projects: https://github.com/wormhole-foundation/xdapp-book/tree/main/projects 
* Setting up wormhole dev environment 
    1. running local testnets and guardians:
       * https://github.com/wormhole-foundation/xdapp-book/tree/main/projects/wormhole-local-validator
    2. running Redis (a queue for storing VAAS) and then the SpyListener/RESTRelayer/WalletMonitor: 
       * https://github.com/wormhole-foundation/wormhole/tree/dev.v2/relayer/spy_relayer
