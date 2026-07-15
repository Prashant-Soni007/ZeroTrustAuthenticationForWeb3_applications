# Adaptive Zero Trust Authentication Framework for Web3 Applications

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status: Accepted for Publication](https://img.shields.io/badge/Status-IEEE%20Publication%20Accepted-brightgreen)]()
[![Python 3.8+](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Solidity 0.8.19+](https://img.shields.io/badge/Solidity-0.8.19+-blue.svg)](https://solidity.readthedocs.io/)

---

## Overview

This repository contains the implementation and research artifacts for the **Adaptive Zero Trust Authentication (AZTA) Framework** — a comprehensive security solution designed to address authentication vulnerabilities in Web3 applications and decentralized finance (DeFi) ecosystems.

The framework combines **Decentralized Identifiers (DIDs)**, **Ethereum-based smart contracts**, and **neural network-driven biometric verification** to enforce continuous "Never Trust, Always Verify" principles in decentralized environments.

### 📰 Publication Status

**The academic paper is currently under registration and has been accepted for publication by IEEE.** The full paper will be available in this repository once it is officially published. Please check back for updates.

---

## 🔐 Key Features

### Core Security Capabilities

- **Zero Trust Architecture**: Continuous authentication and verification for every access attempt
- **Decentralized Identity (DID)**: Self-sovereign identity management without central providers
- **Blind Message Attack Prevention**: 100% interception rate for malicious cryptographic payloads
- **Neuro-Secure Biometrics**: 97.20% authentication accuracy using FaceNet512 neural networks
- **Smart Contract Enforcement**: Immutable, tamper-proof access policy enforcement on Ethereum
- **Multi-Factor Authentication (MFA)**: Context-aware, layered verification mechanisms
- **Privacy-Preserving Design**: Encrypted biometric storage on IPFS with zero on-chain exposure

### Performance Metrics

| Metric | Value |
|--------|-------|
| **Authentication Accuracy** | 97.20% |
| **Average Login Latency** | 1.069 seconds |
| **Zero-Trust Overhead** | +214 ms |
| **False Acceptance Rate** | 0.01% |
| **False Rejection Rate** | 2.80% |
| **Blind Attack Block Rate** | 100% |
| **Credential Theft Block Rate** | 99.99% |

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Web3 Application Layer                    │
│                  (React.js dApp Frontend)                    │
└──────────────────────┬──────────────────────────────────────┘
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
   ┌────────┐    ┌─────────┐    ┌──────────────┐
   │Signature│    │Risk     │    │Biometric    │
   │Engine   │    │Scoring  │    │Verification │
   │(EIP-712)│    │Engine   │    │(N-SAM)      │
   └────────┘    └─────────┘    └──────────────┘
        │              │              │
        └──────────────┼──────────────┘
                       │
        ┌──────────────▼──────────────┐
        │  Ethereum Policy Engine     │
        │  (Smart Contracts - PE/PEP) │
        │  - RBAC Enforcement         │
        │  - MFA/JIT Access Control   │
        │  - Policy Validation        │
        └──────────────┬──────────────┘
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
   ┌────────┐    ┌─────────┐    ┌──────────────┐
   │Ethereum│    │IPFS     │    │DID Registry  │
   │Network │    │Cluster  │    │& VCs         │
   │(PoA)   │    │(go-ipfs)│    │              │
   └────────┘    └─────────┘    └──────────────┘
```

---

## 🛠️ System Components

### 1. **Decentralized Identity & Capability Management**
- Self-Sovereign Identity (SSI) with DIDs
- Capability-Based Access Control (CapBAC)
- Verifiable Credentials (VCs) for delegation

### 2. **Blockchain-Based Policy Engine**
- Solidity smart contracts (v0.8.19+)
- Role-Based Access Control (RBAC)
- Just-In-Time (JIT) access provisioning
- Immutable audit trails

### 3. **Neuro-Secure Authentication Mechanism (N-SAM)**
- Pre-trained FaceNet512 model for feature extraction
- AES-256-GCM encryption for biometric data
- IPFS storage with Kademlia DHT routing
- Cosine similarity matching (threshold: 0.972)

### 4. **Contextual Risk Evaluation**
- Dynamic trust scoring algorithm
- Device health assessment
- IP reputation checking
- Behavioral heuristics analysis

### 5. **Blind Message Attack Defense**
- EIP-712 structured data validation
- Domain signature verification
- Time-based nonce checking
- Cross-application payload verification

---

## 📋 Requirements

### Blockchain & Smart Contracts
- **Ethereum Client**: Go-Ethereum (Geth) v1.13+
- **Consensus**: Proof-of-Authority (PoA)
- **Solidity Compiler**: v0.8.19
- **Development Framework**: Hardhat v2.14+

### Biometric Processing
- **Python**: 3.8+
- **GPU**: NVIDIA GPU (RTX 3060 or better recommended)
- **CUDA**: 11.8+ (for GPU acceleration)
- **TensorFlow/PyTorch**: Latest stable version

### Decentralized Storage
- **IPFS**: go-ipfs v0.20+ (daemon mode)
- **DHT Protocol**: Kademlia

### Frontend & Web3 Integration
- **Node.js**: 16+
- **React.js**: 18+
- **Web3.js**: 1.10+
- **MetaMask**: Browser extension or compatible wallet

### Infrastructure
- **OS**: Ubuntu 22.04 LTS or equivalent
- **Disk Space**: 50+ GB for IPFS node
- **RAM**: 16 GB minimum
- **Network**: Low-latency connection to Ethereum network

---

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/azta-web3-framework.git
cd azta-web3-framework
```

### 2. Install Dependencies

#### Smart Contracts & Blockchain
```bash
cd blockchain
npm install
```

#### Biometric Engine
```bash
cd biometric-engine
pip install -r requirements.txt
python download_facenet512.py
```

#### Frontend dApp
```bash
cd frontend
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory:
```env
# Ethereum Network Configuration
ETHEREUM_RPC_URL=http://localhost:8545
CHAIN_ID=1337
PRIVATE_KEY=your_wallet_private_key

# Smart Contract Addresses
POLICY_ENGINE_ADDRESS=0x...
POLICY_ENFORCEMENT_POINT_ADDRESS=0x...

# IPFS Configuration
IPFS_API_URL=http://localhost:5001
IPFS_GATEWAY_URL=http://localhost:8080

# Biometric Configuration
FACENET_MODEL_PATH=./models/facenet512.pb
COSINE_SIMILARITY_THRESHOLD=0.972
AES_KEY=your_encryption_key

# Risk Scoring Parameters
RISK_THRESHOLD=0.65
```

### 4. Deploy Smart Contracts

```bash
cd blockchain
npx hardhat compile
npx hardhat run scripts/deploy.js --network localhost
```

### 5. Start IPFS Daemon

```bash
ipfs daemon --enable-gc
```

### 6. Launch Biometric Engine

```bash
cd biometric-engine
python app.py --port 5000
```

### 7. Run Frontend dApp

```bash
cd frontend
npm start
```

Access the application at `http://localhost:3000`

---

## 📊 Experimental Results

### Authentication Performance

**Average Latency Breakdown:**
- Client-side cryptographic hashing: ~45 ms
- IPFS template retrieval: ~150 ms
- Smart contract state evaluation: ~19 ms
- **Total authentication time: 1.069 seconds**

### Biometric Accuracy
- **Overall Accuracy**: 97.20%
- **False Acceptance Rate (FAR)**: 0.01%
- **False Rejection Rate (FRR)**: 2.80%
- **Threshold**: Cosine similarity ≥ 0.972

### Gas Consumption
- **Deployment Cost**: ~2,415,000 Gas
- **Per-Authentication Cost**: 45,221 Gas
- **Cost Optimization**: Off-chain IPFS storage + on-chain hashing

### Security Testing
- **Simulated Attacks**: 10,000 blind message attack payloads
- **Block Rate**: 100%
- **Zero Bypass Rate**: 0%

---

## 🔒 Security Analysis

### Attack Vectors & Mitigations

| Attack Type | Traditional Web3 Weakness | AZTA Mitigation |
|---|---|---|
| **Blind Message Attacks** | No payload verification | EIP-712 domain matching + nonce validation |
| **Credential Theft** | Single key compromise = total loss | Biometric + MFA + capability revocation |
| **Session Hijacking** | Indefinite session validity | Context-aware access revocation |
| **Data Tampering** | Centralized DB vulnerability | Encrypted IPFS + immutable on-chain hash |
| **DDoS / Outages** | Centralized IdP single point of failure | Decentralized DIDs & Ethereum resilience |

### Threat Resistance
- ✅ **Blind Message Attacks**: 100% blocked
- ✅ **Credential Theft**: 99.99% prevented
- ✅ **Session Replay**: Fully neutralized
- ✅ **Man-in-the-Browser (MITB)**: Mitigated via on-chain verification
- ✅ **Deepfake Attacks**: Defended by strict FAR calibration

---

## 📚 Technical Documentation

### Smart Contract Architecture

The Policy Engine (`PolicyEngine.sol`) implements:
- Capability delegation with sanitizable signatures
- Dynamic role-based access control (RBAC)
- Multi-factor authentication enforcement
- Just-in-time (JIT) access provisioning
- Audit logging and compliance tracking

### Biometric Matching Algorithm

```
Cosine Similarity(A, B) = Σ(A_i × B_i) / √(Σ A_i²) × √(Σ B_i²)

Where:
  A = Live facial feature vector (512-dimensional, from FaceNet512)
  B = Stored biometric template (decrypted from IPFS)
  n = 512 (embedding dimensionality)

Threshold: τ = 0.972
```

### Risk Scoring Formula

```
T_score = Σ(C_j × w_j) for j=1 to k

Where:
  C_j = Normalized contextual parameter value
  w_j = Cryptographic weight (Σ w_j = 1)
  
Parameters include:
  - Device health score
  - IP reputation
  - Behavioral heuristics
  - Temporal patterns
  - Geographic consistency
```

---

## 🚧 Limitations & Future Work

### Current Limitations

1. **Web2 Infrastructure Trust Gap**: dApp UIs often run on centralized servers (DNS hijacking risk)
2. **Hardware Requirements**: Biometric extraction requires capable edge NPUs
3. **Deepfake Resilience**: Growing AI-generated spoofing threats require continuous updates
4. **Latency Trade-off**: 214 ms overhead vs. traditional Web3 authentication

### Future Enhancements

- **Zero-Knowledge Proofs (zk-SNARKs)**: Replace AES-IPFS hashing with mathematical proof of biometric match
- **Quantum-Resistant Cryptography**: Migrate from ECDSA to lattice-based signatures
- **Federated Learning**: Deploy edge-based deepfake detection models
- **Cross-Chain Compatibility**: Extend framework to Layer-2 networks and alternative L1 blockchains
- **Hardware Wallet Integration**: Native support for hardware-backed key management

---

## 📖 Citation & References

If you use this framework in your research, please cite:

```bibtex
@article{AZTA2025,
  title={Adaptive Zero Trust Authentication Model for Web3 Applications},
  author={[Author Names - Will be Updated Upon Publication]},
  journal={IEEE [Journal Name]},
  year={2025},
  status={Accepted for Publication}
}
```

For detailed references and related work, see the **References** section in the full paper.

---

## 📄 Paper Publication

**Current Status**: 🟢 **Accepted for Publication by IEEE**

The full academic paper is currently under registration with IEEE and will be available in this repository once officially published. Subscribe to this repository to receive notifications when the paper is released.

**Expected Publication Timeline**: Q3-Q4 2025

---

## 🤝 Contributing

We welcome contributions from the research community. Please follow these guidelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Submit a pull request with detailed description

---

## 📞 Contact & Support

For questions, bug reports, or collaboration inquiries:

- **GitHub Issues**: [Report bugs or request features](https://github.com/yourusername/azta-web3-framework/issues)
- **Discussion Forum**: [Join community discussions](https://github.com/yourusername/azta-web3-framework/discussions)
- **Email**: [research contact - to be added upon publication]

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

We thank:
- The Ethereum Foundation for blockchain infrastructure
- IPFS and Protocol Labs for decentralized storage solutions
- The open-source community for TensorFlow, PyTorch, and Web3.js
- All contributors and reviewers who helped refine this framework

---

## ⚠️ Disclaimer

This framework is provided for **research and educational purposes**. While extensive security testing has been performed, users should conduct their own security audits before deploying in production environments. The authors are not responsible for losses or damages resulting from the use of this software.

---

**Last Updated**: July 2025  
**Status**: 🟢 IEEE Publication Accepted | ⏳ Paper Pending Upload  
**Version**: 1.0.0 (Beta)

---

*For the latest updates and developments, please star 🌟 this repository and follow our releases.*
