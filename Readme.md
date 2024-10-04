# Tonswap - FunC Smart Contracts

## TonSwap is live on TON mainnet.

TonSwap is currently live on the TON mainnet and is in beta, so please use it at your own risk.

## Overview

TonSwap is a decentralized exchange (DEX) and automated market maker (AMM) that utilizes the Uniswap V2 curve, a financial model commonly used by popular AMMs like PancakeSwap, QuickSwap, and Sushi. This platform enables traders to swap tokens and allows liquidity providers to supply liquidity and earn rewards.

## Develop

run `npm install`

### Compile contract and run tests

This project depends on the executables **fift**, **func** . You can build them from [source](https://ton.org/docs/#/howto/getting-started), or you can download the [pre compiled binaries](https://github.com/ton-defi-org/ton-binaries/releases).

### Func Compiler

This project is using the latest func features such as `#include` and `const` so please use the latest func compiler ,
If you want to set an explicit func path you may use the FUNC_PATH environment variable `export FUNC_PATH=/usr/local/bin/func`

### Run tests

the project uses [ton-contract-executor](https://github.com/tonwhales/ton-contract-executor) package to run Jest based tests.
Use `npm run test` to execute the test suite.

### Run TVM-BUS tests

run `npm run test-bus` 
this tests are different then the tests in `/test/amm-minter.spec.ts`, 
Because this tests are using [ton-tvm-bus](https://github.com/ton-defi-org/ton-tvm-bus) , each tests starts in a single message, and the message passing between contracts is done automatically, messages with statInit are auto deployed , messages find their receiver automatically unlike in the first test suite.


### Run end to end test on Mainnet or Testnet

`npm run e2e` (this process will generate a deploy wallet during it`s execution)

### build for web 

`npm run build:web` - this process will generate json files with hex value for the contract, both for `amm-minter.fc` and `amm-wallet.fc`;
