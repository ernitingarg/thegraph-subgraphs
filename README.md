# Overview

This document explains how to initialize, create, and deploy your subgraph to the sandbox [Subgraph Studio](https://thegraph.com/studio/) which can be published to hosted service once testing is done.

0. Prerequisite

   - Connect [Subgraph Sudio](https://thegraph.com/studio/) with wallet (eg: metamask)
   - Create API key

1. Install Graph CLI with either npm or yarn

```bash
npm install -g @graphprotocol/graph-cli

yarn global add @graphprotocol/graph-cli
```

2. Run below command to create new subgraph for existing smart contract. Below example creates the subgraph for [uniswap](https://etherscan.io/token/0x1f9840a85d5af5bf1d1762f925bdaddc4201f984) smart contract.

```bash
graph init --protocol ethereum --network goerli --from-contract 0x1f9840a85d5aF5bf1D1762F925BDADdC4201F984 --contract-name UNI --studio --index-events subgraph_slug_name subgraph_directory
```

3. Authenticate within CLI by providing Subgraph Studio API key

```bash
graph auth --studio <api_key>
```

4. Go to subgraph directory

```bash
cd subgraph_directory
```

5. Build the subgraph

```bash
graph codegen && graph build
```

6. Deploy subgraph to Subgraph Studio

```bash
graph deploy --studio subgraph_slug_name
```

7. You can access and use playground for the deployed subgraph at below url

```bash
https://thegraph.com/studio/subgraph/subgraph_slug_name/
```
