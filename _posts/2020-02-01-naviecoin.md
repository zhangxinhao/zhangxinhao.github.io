---
date: 2020-02-01 14:00
layout: post
title: "Naivecoin 一个区块链的简易实现"
author: "xinhao"
header-style: text
tags:
  - Blockchain
---

# 简介

**Naivecoin** 是一个区块链的简易实现。直接去看比特币或者以太坊的源码来理解区块链是比较困难的，**Naivecoin** 包含基本的功能，方便你更好的理解区块链的实现。 详见 [Naivecoin](https://lhartikk.github.io/)

# 效果展示

运行起来的区块链可以直接使用命令行进行操作，也可以使用 Web GUI 进行操作。以下是区块链浏览器和钱包的样例：

区块链浏览器：

![img](/img/btc/Naivecoin/blockchainexplorer.png)

区块：

![img](/img/btc/Naivecoin/Block.png)

交易：

![img](/img/btc/Naivecoin/Transaction.png)

地址：

![img](/img/btc/Naivecoin/Address.png)

钱包：

![img](/img/btc/Naivecoin/Naivecoinwallet.png)

# 运行

**Naivecoin** 的编程语言是 **Typescript**，**Web GUI** 使用 Vue.js 框架。首先确保你已经安装了 node 的开发环境。

**Naivecoin**：

    git clone https://github.com/lhartikk/naivecoin.git
    cd naivecoin
    npm install
    npm start

    # Get blockchain
    curl http://localhost:3001/blocks

    # Mine a block
    curl -X POST http://localhost:3001/mineBlock

    # Send transaction
    curl -H "Content-type: application/json" --data '{"address": "04bfcab8722991ae774db48f934ca79cfb7dd991229153b9f732ba5334aafcd8e7266e47076996b55a14bf9913ee3145ce0cfc1372ada8ada74bd287450313534b", "amount" : 35}' http://localhost:3001/sendTransaction

    # Query transaction pool
    curl http://localhost:3001/transactionPool

    # Mine transaction
    curl -H "Content-type: application/json" --data '{"address": "04bfcab8722991ae774db48f934ca79cfb7dd991229153b9f732ba5334aafcd8e7266e47076996b55a14bf9913ee3145ce0cfc1372ada8ada74bd287450313534b", "amount" : 35}' http://localhost:3001/mineTransaction

    # Get balance
    curl http://localhost:3001/balance

    # Query information about a specific address
    curl http://localhost:3001/address/04f72a4541275aeb4344a8b049bfe2734b49fe25c08d56918f033507b96a61f9e3c330c4fcd46d0854a712dc878b9c280abe90c788c47497e06df78b25bf60ae64

    # Add peer
    curl -H "Content-type:application/json" --data '{"peer" : "ws://localhost:6001"}' http://localhost:3001/addPeer

    # Query connected peers
    curl http://localhost:3001/peers

**naivecoin-explorer**:

    git clone https://github.com/lhartikk/naivecoin-ui.git
    cd naivecoin-ui/naivecoin-explorer
    # install dependencies
    npm install

    # serve with hot reload at localhost:8080
    npm run dev

    # build for production with minification
    npm run build

**naivecoin-wallet**:

    git clone https://github.com/lhartikk/naivecoin-ui.git
    cd naivecoin-ui/naivecoin-wallet
    # install dependencies
    npm install

    # serve with hot reload at localhost:8080
    npm run dev

    # build for production with minification
    npm run build

