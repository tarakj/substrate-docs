---
title: Blockchain basics
description: Introduces common blockchain concepts, components, and terminology.
featured_image:
---

A blockchain is a public ledger that records digital transactions. No central authority controls the blockchain i.e. it is decentralized. Transactions posted to the blockchain are recorded in a sequence of encrypted blocks. These blocks are immutable. The blockchain is distributed across a global network of connected computers.

In a blockchain network, individual computers—called nodes—communicate with each other to form a decentralized peer-to-peer (P2P) network.
Nodes store a copy of the  blocks that make up the canonical chain, help validate transactions and post new transactions to the public ledger.

In most cases, users interact with a blockchain by initiating transaction requests. 
New transactions are assembled into a block by a participating node known as the block author. Then they are broadcast or gossiped to other nodes on the network.
To ensure the security of the data on the chain and its ongoing progress, the nodes use some form of consensus model to agree on the state of the data in each block and the order in which transactions are processed.

## What is a blockchain node?

Nodes run the blockchain source code. A node may be a full node or a validator node (aka light node). 

At a high level, nodes have the following components:

- Data storage for the state changes recorded as a result of transactions.
- Networking capabilities for decentralized communication with other nodes.
- Appropriate computing power and execution environment for the blockchain software.

The blockchain software implements the blockchain logic providing:

- A consensus model to protect against malicious activity and ensure progress of the chain.
- Logic for ordering and processing incoming transactions.
- Cryptography for signing and verifying the signatures associated with transactions.
- Logic for authoring and finalizing blocks to communicate with the p2p network.

## What is Substrate?

Blockchain technology has been developed painstakingly over several years. At the time of writing this, it is still under rapid, iterative development.

Because of the complexity involved in building the core components a blockchain requires, most blockchains start with a complete copy of an existing blockchain repository—a fork—so that developers can modify existing code to add new features instead of writing everything from scratch.
For example, the Bitcoin repository was forked to create Litecoin, ZCash, Namecoin and Bitcoin Cash.
Similarly, the Ethereum repository was forked to create Quorum, POA Network, KodakCoin, and Musicoin.

However, most blockchain platforms are not designed to allow for modification or customization.
As a result, building a new blockchain by forking has serious limitations, including limitations such as scalability that are inherent in the originating blockchain code. Substrate is a blockchain framework designed to enable developers to create their own customized blockchains (aka parachains).

Before you explore how Substrate alleviates many of the limitations associated with other blockchain projects, it's important to understand some of the common properties that all blockchains share.
By learning about how most blockchains operate, you'll be better prepared to see how Substrate provides alternatives and capabilities for building a blockchain best suited to your needs.  

## State transitions and conflicts

A blockchain is essentially a [state machine](https://en.wikipedia.org/wiki/Finite-state_machine). 
At any point in time, the blockchain has a current internal state.
As inbound transactions are executed, they result in changes to state so the blockchain must transition from its current state to a new state. 
However, there can be multiple valid transitions that would result in different future states, and the blockchain must select a single state transition that can be agreed upon.
To agree on the state after a transition, all operations within a blockchain must be deterministic.
For the chain to progress successfully, a majority of the nodes must agree on all of the state transitions, including:

- The initial state of the chain, called the genesis state or genesis block.
- The series of state transitions that result from executed transactions that are recorded in each block.
- A final state for the block to be included in the chain.

In centralized networks, a central authority can choose between mutually exclusive state transitions by recording the changes to state transition in the order it sees them, and choosing the first of the competing alternatives when a conflict arises. 
In a decentralized network, the nodes see transactions in different orders, so they must use a more elaborate method to select transactions and choose between conflicting state transition. 

The method that a blockchain uses to batch transactions into blocks and to select which node can submit a block to the chain is called the blockchain's consensus model or consensus algorithm. 
The most commonly-used consensus model is the proof of work consensus model. 
With the proof of work consensus model, the node that completes a mathematical problem first has the right to submit a block to the chain. A proof of stake consensus model is currently under development to solve some challenges posed by proof of work.

For a blockchain to be fault tolerant and provide a consistent view of state even if some nodes are compromised by malicious actors or network outages, most consensus models require at least two-thirds of the nodes agree on state at all times. 
This two-thirds majority ensures that the network is fault tolerant and can withstand some compromised network participants, regardless of whether the behavior is intentional or accidental. The system is secure as long as honest nodes control more CPU power than any cooperating group of compromised nodes.

## Signing a transaction

Users who want to make transactions have accounts associated with keys. Upon joining the network, users are assigned a randomly generated seed which works as a wallet. The seed in turn generates private and public keys. The keys are used to derive addresses. The addresses are associated with an account. The account address is used to receive funds. The private keys are used to sign the transactions posted to the ledger. The seed and private keys should not be shared. The private key is used to sign transactions and the corresponding public key can verify the signature. These concepts are borrowed from public-key cryptography.

Some exchanges or hosted wallets may abstract the process of random seed generation from their users. Since the transfer of funds is associated with the user's address, the account keeps a track of their balances and/or digital assets transferred to them. 

While the blockchain inherently does not require people identities to be associated with accounts, governments all over the world are beginning to require this.

## Blockchain economics

All blockchains require resources—processors, memory, storage, and network bandwidth—to perform operations.
The computers that participate in the network—the nodes that produce blocks—provide these resources to blockchain users.
The nodes create a distributed, decentralized network that serves the needs of a community of participants.

To support a community and make a blockchain sustainable, most blockchains require users to pay for the network resources they use in the form of transaction fees.
Blockchains typically use tokens to represent the value of assets in an account and network participants purchase tokens outside of the chain through an exchange.
Network participants can then deposit the tokens to create a stake of funds that enable them to pay for transactions.

## Blockchain governance

Most blockchains also enable network participants to submit and vote on proposals that affect network operations or the blockchain community.
By submitting and voting on proposals—referenda—the blockchain community can determine how the blockchain evolves in an essentially democratic process.
To participate in governance, however, most blockchains require users to maintain a significant stake of token in an account.

## Applications running on a blockchain

Applications that run on a blockchain—often referred to as decentralized applications or dApps—are typically written as **smart contracts**. 

A smart contract is a program that runs on a blockchain and executes transactions on behalf of users under specific conditions.
Developers can write smart contracts to ensure that the outcome of programmatically-executed transactions is recorded and can never be changed. 
Yet, with smart contracts alone, developers don't have access to some underlying blockchain functionality—such as the consensus, storage or transaction layers—and instead, abide by a chain's fixed rules and restrictions.
Smart contract developers often accept these limitations as a tradeoff that enables faster development time with fewer core design decisions to make.

## Where to go next

All blockchains share some common characteristics. 
Substrate—while not a blockchain itself—is a blockchain builders' toolkit with a modular framework of components to create a custom blockchain. 
With Substrate, you can take the common blockchain components—like storage and consensus and cryptography—and combine them to use the functions they provide as-is or modify them to suit the purpose of your project. 

You can explore the following resources to learn more.

#### Tell me

* [why Substrate?](/main-docs/why-substrate/)
* [Fundamentals](main-docs/fundamentals/)
* [Architecture](main-docs/fundamentals/architecture/)
* [Networks and blockchains](main-docs/fundamentals/node-and-network-types/)

#### Guide me

* [Build a local blockchain](/tutorials/get-started/build-local-blockchain/)
* [Simulate a network](/tutorials/get-started/simulate-network/)
* [Add trusted validators](/tutorials/get-started/trusted-network/)

If you prefer to explore code directly, you can start building in the Developer Playground and consult the API reference to get details about the Rust crates you use.
