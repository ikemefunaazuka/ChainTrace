# ChainTrace

A shipment custody record. A batch of goods changes hands between a Producer, a Carrier and a Distributor, and every transfer plus supporting documents like a certificate of origin or an inspection report is recorded immutably and can be verified independently by anyone in the chain.

Status: building now. Not shipped yet, and not live with users yet.

Why a blockchain at all: custody between parties who do not run each other's databases and do not fully trust each other's paperwork. Each transfer is signed by the current holder, recorded immutably, and verifiable independently. Reads come from an indexer, not from querying the chain directly.

Roadmap

• Custody smart contract with holder only transfers and role based access for Producer, Carrier and Auditor, plus tests
• Reentrancy hardening and a Slither audit pass
• Frontend that reads the custody chain without a wallet and submits transfers with pending, confirmed and failed states clearly shown
• Indexer plus shipment history API
• README, architecture notes, and an honest note on what a plain database version would change

Tech: Solidity, Hardhat, OpenZeppelin AccessControl, React, PostgreSQL, IPFS, Slither

Licence: MIT
