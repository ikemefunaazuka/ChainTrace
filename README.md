**Note on current state:** this repo is intentionally at scaffold stage, with the README, roadmap and licence in place first and code landing as the build proceeds. My larger production codebases belong to employers and clients, so they are not mine to publish here. This project is separate from all of them, owned by me alone, and not owned by any company.

# ChainTrace

A shipment custody record, built to an industry standard.

A batch of goods changes hands between a Producer, a Carrier and a Distributor, and every transfer plus supporting documents like a certificate of origin or an inspection report is recorded immutably and can be verified independently by anyone in the chain. A wallet signs each transfer, a smart contract records it, an indexer mirrors events into a normal database, and a shipment history API serves reads without touching the chain directly. Documents live on IPFS, with only their hash stored on chain.

Status: building now. Not shipped yet, and not live with users yet.

Why a blockchain at all: custody between parties who do not run each other's databases and do not fully trust each other's paperwork. A shared database owned by one party would leave the other parties trusting that owner's records. Here, each transfer is signed by the current holder, recorded immutably, and verifiable independently, while reads come from the indexer, not from querying the chain directly.

Planned work: 200 hours of independent development in total.

Roadmap

• Contract suite covering custody, roles, document hashes, multi shipment handling, and return flows, plus full test coverage: 45 hours
• Security work: reentrancy hardening, invariant and fuzz testing, Slither plus manual review, and audit fixes: 35 hours
• Frontend: dashboard, shipment list and detail views, wallet connection, transfer flow with pending, confirmed and failed states: 45 hours
• Backend: indexer, history API, auth, pagination, search, and error handling: 40 hours
• Deployment, CI/CD, monitoring, docs, and the checkpoint demo: 35 hours

Planned layout

• contracts: custody contract and role based access
• app: dashboard and transfer flow
• indexer: event listener plus shipment history API
• docs: architecture notes and audit reports

Done looks like: a tested contract on a test network, a working dashboard, an indexer serving shipment history, a clean audit pass, and docs that explain why a blockchain at all and what a plain database version would change.

Tech: Solidity, Hardhat, OpenZeppelin AccessControl, React, PostgreSQL, IPFS, Slither

Licence: MIT
