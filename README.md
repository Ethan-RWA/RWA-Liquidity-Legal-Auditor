> **⚠️ Note: This repository is currently in active migration.** > The core auditing logic is being refactored from private research scripts into this public framework. 
> The skeleton is up, and the specific extraction modules are being pushed incrementally this week.

# RWA Liquidity & Legal Auditor 🔍

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Research%20Preview-orange)]()

## 📜 Abstract

The **RWA-Liquidity-Auditor** is a research-grade tool designed to bridge the gap between **on-chain finality** and **off-chain legal enforceability**.

In the current Real World Asset (RWA) landscape, protocols often market "Instant Liquidity" via smart contracts, while their Terms of Service (ToS) legally restrict secondary market trading or impose T+2 settlement delays. This tool uses **Vector Embeddings (RAG)** to parse PDF legal documents and cross-reference them with Solidity withdrawal functions to detect contradictory logic.

## 🏗️ Architecture

1.  **Legal Ingestion Layer**: Parses PDF/Docx Terms of Service using `pypdf`.
2.  **Clause Extraction**: Uses NLP to identify "Liquidity", "Redemption", and "Settlement" clauses.
3.  **On-Chain Verification**: Connects to RPC nodes to simulate `withdraw()` function gas limits and logic barriers.
4.  **Discrepancy Engine**: Flags where `Code != Law`.

## 🚀 Quick Start (Alpha)

```bash
# Clone the repository
git clone [https://github.com/Ethan-RWA/RWA-Liquidity-Legal-Auditor.git](https://github.com/Ethan-RWA/RWA-Liquidity-Legal-Auditor.git)

# Install dependencies
pip install -r requirements.txt

# Run the auditor (Example)
python auditor.py --target "0xOndoContractAddress..." --legal_doc "./docs/terms.pdf"
