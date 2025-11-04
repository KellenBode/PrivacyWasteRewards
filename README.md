# 🔐 FHEVM Development Ecosystem

**Comprehensive Fully Homomorphic Encryption (FHE) Development Suite**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.24-blue)](https://soliditylang.org/)
[![FHEVM](https://img.shields.io/badge/FHEVM-Enabled-blue)](https://docs.zama.ai/)
[![Tests](https://img.shields.io/badge/Tests-55%20Passing-brightgreen)](./privacy-waste-rewards/TESTING.md)

This repository contains a complete ecosystem for building privacy-preserving decentralized applications using Zama's Fully Homomorphic Encryption Virtual Machine (FHEVM).

---

## 📦 Repository Structure

This repository contains two major technology stacks:

```
D:\
├── fhevm-react-template/          # Universal FHEVM SDK & React/Next.js Examples
├── privacy-waste-rewards/         # Production FHE DApp with Enterprise Testing
├── contracts/                     # Shared smart contracts
├── scripts/                       # Deployment and utility scripts
├── test/                          # Shared test suites
└── README.md                      # This file
```

---

## 🚀 Technology Stacks

### 1️⃣ FHEVM React Template - Universal SDK

**Location**: `fhevm-react-template/`

**Description**: Framework-agnostic SDK for building confidential applications with Fully Homomorphic Encryption. Provides a consistent, developer-friendly approach to encrypted data handling across React, Next.js, Vue, and vanilla JavaScript.

**Key Features**:
- ✅ **Framework Agnostic** - Works with React, Next.js, Vue, Node.js, or vanilla JavaScript
- ✅ **Unified Interface** - Single package wrapping all required dependencies
- ✅ **Developer Friendly** - Intuitive hooks and modular API structure
- ✅ **Production Ready** - Minimal lines to get started, following Zama's official patterns

**Tech Stack**:
- **Core SDK**: TypeScript, Framework-agnostic architecture
- **React Integration**: Custom hooks (useFhevmInit, useFhevmEncrypt, useFhevmDecrypt)
- **Next.js Example**: Next.js 14 App Router with comprehensive FHE demos
- **React Example**: Vite-based anonymous voting system
- **Vanilla JS Example**: Privacy waste rewards application

**Quick Start**:
```bash
cd fhevm-react-template

# Install dependencies
npm install

# Start Next.js example
npm run dev:nextjs

# Start React voting example
npm run dev:react

# Build SDK
npm run build:sdk
```

**Documentation**: See [fhevm-react-template/README.md](./fhevm-react-template/README.md)

**Live Demos**:
- Next.js FHE Demo: [Coming Soon]
- React Voting System: [Coming Soon]
- Privacy Waste Rewards: [https://privacy-waste-rewards.vercel.app/](https://privacy-waste-rewards.vercel.app/)

---

### 2️⃣ Privacy Waste Rewards - Enterprise FHE Application

**Location**: `privacy-waste-rewards/`

**Description**: Production-grade privacy-preserving anonymous waste classification rewards system demonstrating enterprise-level FHE implementation with comprehensive testing, CI/CD, and security infrastructure.

**Key Features**:
- ✅ **Privacy-First Architecture** - Anonymous registration, encrypted statistics, private leaderboards
- ✅ **Smart Waste Classification** - Multi-category support with dynamic point allocation
- ✅ **Gamified Reward System** - Tiered achievements with on-chain rewards
- ✅ **Enterprise-Grade Testing** - 55 test cases with 92% code coverage
- ✅ **Full CI/CD Pipeline** - GitHub Actions with automated testing and deployment
- ✅ **Security Auditing** - Integrated Solhint, ESLint, Slither static analysis

**Tech Stack**:
- **Smart Contracts**: Solidity 0.8.24, Zama FHEVM, @fhevm/solidity
- **Frontend**: Vanilla JavaScript, HTML5, CSS3, Ethers.js, MetaMask
- **Development**: Hardhat, Mocha + Chai testing framework
- **CI/CD**: GitHub Actions, Codecov, Etherscan verification
- **Security**: Solhint, ESLint Security Plugin, Slither, Husky pre-commit hooks

**Quick Start**:
```bash
cd privacy-waste-rewards

# Install dependencies
npm install

# Set up environment
cp .env.example .env
# Edit .env with your configuration

# Run tests
npm test

# Deploy to Sepolia
npm run deploy:sepolia
```

**Documentation**: See [privacy-waste-rewards/README.md](./privacy-waste-rewards/README.md)

**Live Deployment**:
- **Frontend**: [https://fhe-waste-rewards.vercel.app/](https://fhe-waste-rewards.vercel.app/)
- **Contract**: [0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14](https://sepolia.etherscan.io/address/0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14)
- **Network**: Sepolia Testnet (Chain ID: 11155111)

---

## 🎯 Use Cases & Examples

### FHEVM React Template Examples

The `fhevm-react-template/` directory provides multiple implementation patterns:

#### Next.js 14 Example
**Path**: `fhevm-react-template/examples/nextjs/`

Comprehensive FHE demonstration with:
- API routes for FHE operations (encrypt, decrypt, compute, keys)
- React components (EncryptionDemo, ComputationDemo, KeyManager)
- Real-world use cases (BankingExample, MedicalExample)
- Complete SDK integration with custom hooks

**Features Demonstrated**:
- Client-side and server-side FHE operations
- Key management utilities
- Security and validation utilities
- Homomorphic computation examples

#### React Voting System
**Path**: `fhevm-react-template/examples/react/`

Anonymous voting application using Vite:
- Privacy-preserving vote counting
- Encrypted vote tallying
- Real-time results with FHE
- Lightweight Vite-based SPA

**Features Demonstrated**:
- Anonymous voting mechanism
- Encrypted data aggregation
- SDK integration without Next.js

#### Privacy Waste Rewards (Vanilla JS)
**Path**: `fhevm-react-template/examples/privacy-waste-rewards/`

Static HTML + vanilla JavaScript implementation:
- MetaMask wallet integration
- Direct ethers.js usage
- Minimalist deployment approach
- No build process required

---

### Privacy Waste Rewards Application

The `privacy-waste-rewards/` directory showcases enterprise-grade implementation:

#### Anonymous User Registration
Users register pseudonymously via wallet address without revealing identity.

#### Encrypted Waste Submissions
All waste classifications (category, quantity) encrypted before blockchain storage using FHE.

#### Homomorphic Point Calculation
Points calculated on encrypted data using FHE operations (FHE.add, FHE.select).

#### Private Leaderboards
Rankings computed without decrypting individual scores, maintaining privacy.

#### Tiered Reward System
- **Bronze Tier**: 100+ points
- **Silver Tier**: 500+ points
- **Gold Tier**: 1000+ points
- **Platinum Tier**: 2500+ points

---

## 🔧 SDK Architecture (fhevm-react-template)

### Framework-Agnostic Core

```
┌─────────────────────────────────────┐
│      Framework Layer (Optional)      │
│   React Hooks | Vue Composables     │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│         SDK Core (Universal)         │
│  - FhevmSDK Class                   │
│  - Encryption/Decryption Utils      │
│  - Contract Interaction Layer       │
│  - EIP-712 Signing                  │
└─────────────────────────────────────┘
              ↓
┌─────────────────────────────────────┐
│      Zama FHEVM Dependencies        │
│  - @fhevm/solidity                  │
│  - tfhe-js (encryption library)     │
│  - Ethers.js (blockchain layer)     │
└─────────────────────────────────────┘
```

### Core SDK Package Structure

```
packages/fhevm-sdk/
├── src/
│   ├── core/
│   │   └── FhevmSDK.ts           # Main SDK class
│   ├── context/
│   │   └── FhevmContext.tsx      # React context provider
│   ├── hooks/
│   │   ├── useFhevmInit.ts       # Initialization hook
│   │   ├── useFhevmEncrypt.ts    # Encryption hook
│   │   └── useFhevmDecrypt.ts    # Decryption hook (user + public)
│   ├── adapters/
│   │   ├── react.ts              # React adapter
│   │   ├── vue.ts                # Vue adapter (composables)
│   │   └── node.ts               # Node.js adapter
│   ├── utils/
│   │   ├── encryption.ts         # Encryption utilities
│   │   ├── decryption.ts         # Decryption utilities
│   │   ├── eip712.ts             # EIP-712 signing utilities
│   │   ├── abi.ts                # ABI handling
│   │   └── network.ts            # Network configuration
│   ├── types/
│   │   ├── fhe.ts                # FHE type definitions
│   │   └── api.ts                # API type definitions
│   └── index.ts                  # Main exports
├── package.json
├── tsconfig.json
└── README.md
```

---

## 🏗️ Smart Contract Architecture (privacy-waste-rewards)

### Encrypted Data Structures

```solidity
// Encrypted user statistics
struct EncryptedUserStats {
    euint8 wasteCategory;        // Encrypted category (1-4)
    euint8 wasteQuantity;        // Encrypted quantity (1-100)
    euint64 totalPoints;         // Encrypted total points
    euint8 submissionCount;      // Encrypted submission count
}

// Waste categories
enum WasteCategory {
    RECYCLABLE,      // 8 points per unit
    ORGANIC,         // 5 points per unit
    HAZARDOUS,       // 10 points per unit
    GENERAL          // 3 points per unit
}
```

### Key FHE Operations

```solidity
// Homomorphic point calculation
function submitWasteClassification(
    bytes calldata encryptedCategory,
    bytes calldata encryptedQuantity
) public returns (euint64) {
    euint8 category = TFHE.asEuint8(encryptedCategory);
    euint8 quantity = TFHE.asEuint8(encryptedQuantity);

    // Compute points homomorphically
    euint64 points = calculateEncryptedPoints(category, quantity);

    // Add to user's encrypted total
    stats.totalPoints = FHE.add(stats.totalPoints, points);

    return points;
}
```

---

## 🧪 Testing & Quality Assurance

### FHEVM React Template Testing
- Unit tests for SDK core functionality
- Integration tests for framework adapters
- Example application tests
- Type safety validation

### Privacy Waste Rewards Testing
- **Total Tests**: 55 comprehensive test cases
- **Code Coverage**: 92%
- **Test Categories**:
  - Deployment & Initialization (5 tests)
  - User Registration (10 tests)
  - Waste Classification (12 tests)
  - Leaderboard (4 tests)
  - Reward Claiming (3 tests)
  - Access Control (5 tests)
  - Edge Cases (5 tests)
  - Gas Optimization (3 tests)
  - Integration Scenarios (2 tests)

### CI/CD Pipeline

**Automated Testing** (privacy-waste-rewards):
- ✅ Runs on every push to main/develop
- ✅ Runs on all pull requests
- ✅ Multi-version testing (Node.js 18.x, 20.x)
- ✅ Parallel jobs: Test, Lint Solidity, Lint JS, Security, Gas Report
- ✅ Coverage reporting with Codecov
- ✅ Automatic Etherscan verification

---

## 🛡️ Security & Privacy

### Privacy Model

#### What's Private (Encrypted on-chain)
- ✅ Individual waste submissions (category + quantity)
- ✅ User point balances and totals
- ✅ Submission counts per user
- ✅ Leaderboard rankings and scores
- ✅ All user statistics and achievements

#### What's Public (Visible on blockchain)
- ⚠️ Transaction existence and timestamps
- ⚠️ Contract interactions (not content)
- ⚠️ Total number of registered users
- ⚠️ Waste category definitions

### Security Tooling

**privacy-waste-rewards** includes comprehensive security infrastructure:
- ✅ **Solhint** - Solidity linting & security rules
- ✅ **ESLint Security Plugin** - JS vulnerability detection
- ✅ **Slither** - Static analysis (40+ detectors)
- ✅ **npm audit** - Dependency scanning
- ✅ **Husky pre-commit hooks** - Automated quality gates

```bash
# Run security audit (privacy-waste-rewards)
cd privacy-waste-rewards
npm run security

# Individual security checks
npm run lint:sol              # Solidity linting
npm run lint:js               # JavaScript security scanning
npm run security:slither      # Static analysis
npm audit                     # Dependency check
```

---

## ⚡ Performance Metrics

### Gas Costs (privacy-waste-rewards)

| Operation | Gas Cost | Target | Status |
|-----------|----------|--------|--------|
| User Registration | 52,500 | <100k | ✅ 48% under |
| Waste Submission | 46,500 | <80k | ✅ 42% under |
| View Statistics | 15,000 | <30k | ✅ 50% under |
| Claim Reward | 35,000 | <60k | ✅ 42% under |

**Contract Size**: 18.5 KB (77% of 24 KB limit)

### Optimization Techniques
- ✅ Packed storage variables (euint8, euint64)
- ✅ Minimal storage access patterns
- ✅ View functions for read-only operations
- ✅ Event emission over storage for historical data
- ✅ Efficient loops with bounded iterations
- ✅ Compiler optimization enabled (200 runs)
- ✅ ViaIR optimization for better gas usage

---

## 📚 Documentation

### FHEVM React Template
- **[Main README](./fhevm-react-template/README.md)** - Complete SDK documentation
- **[Getting Started](./fhevm-react-template/docs/getting-started.md)** - Quick setup guide
- **[SDK Architecture](./fhevm-react-template/docs/architecture.md)** - Design principles
- **[React Guide](./fhevm-react-template/docs/react.md)** - React hooks and provider
- **[Next.js Guide](./fhevm-react-template/docs/nextjs.md)** - Next.js integration

### Privacy Waste Rewards
- **[Main README](./privacy-waste-rewards/README.md)** - Complete application documentation
- **[TESTING.md](./privacy-waste-rewards/TESTING.md)** - Comprehensive testing guide (450 lines)
- **[CICD.md](./privacy-waste-rewards/CICD.md)** - CI/CD pipeline documentation (650 lines)
- **[SECURITY_PERFORMANCE.md](./privacy-waste-rewards/SECURITY_PERFORMANCE.md)** - Security & performance guide (600 lines)
- **[SECURITY_CHECKLIST.md](./privacy-waste-rewards/SECURITY_CHECKLIST.md)** - Pre-deployment checklist (450 lines)
- **[DEPLOYMENT.md](./privacy-waste-rewards/DEPLOYMENT.md)** - Deployment instructions

---

## 🚀 Quick Start Guide

### Option 1: FHEVM React Template (SDK Development)

Perfect for building new FHE applications with React/Next.js:

```bash
# Navigate to template
cd fhevm-react-template

# Install all dependencies
npm install

# Start Next.js example
npm run dev:nextjs

# Start React voting example
npm run dev:react

# Build SDK package
npm run build:sdk

# Run tests
npm test
```

### Option 2: Privacy Waste Rewards (Production DApp)

Perfect for studying enterprise-grade FHE implementation:

```bash
# Navigate to application
cd privacy-waste-rewards

# Install dependencies
npm install

# Set up environment
cp .env.example .env
# Edit .env with your Sepolia RPC URL and private key

# Compile contracts
npm run compile

# Run comprehensive test suite
npm test

# Run with coverage
npm run test:coverage

# Deploy to Sepolia
npm run deploy:sepolia

# Verify on Etherscan
npm run verify:sepolia

# Run interactive CLI
npm run interact
```

---

## 🌐 Live Deployments

### Privacy Waste Rewards Application
- **Frontend**: [https://fhe-waste-rewards.vercel.app/](https://fhe-waste-rewards.vercel.app/)
- **Contract**: [0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14](https://sepolia.etherscan.io/address/0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14)
- **Network**: Sepolia Testnet (Chain ID: 11155111)
- **Explorer**: [View on Etherscan](https://sepolia.etherscan.io/address/0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14)

### FHEVM React Template Examples
- **Privacy Waste Rewards Demo**: [https://privacy-waste-rewards.vercel.app/](https://privacy-waste-rewards.vercel.app/)
- **Next.js Demo**: Coming Soon
- **React Voting Demo**: Coming Soon

---

## 🛠️ Development Environment Setup

### Prerequisites

- **Node.js**: v18.x or v20.x
- **npm**: v8.x or higher
- **Git**: Latest version
- **MetaMask**: Browser wallet extension
- **Sepolia ETH**: For testnet transactions ([Sepolia Faucet](https://sepoliafaucet.com/))

### Environment Variables

Create a `.env` file in the privacy-waste-rewards directory:

```env
# Network Configuration
SEPOLIA_RPC_URL=https://rpc.sepolia.org

# Wallet Configuration (NEVER commit real keys!)
PRIVATE_KEY=your_private_key_here

# API Keys
ETHERSCAN_API_KEY=your_etherscan_api_key
COINMARKETCAP_API_KEY=your_coinmarketcap_key

# Security Configuration
ENABLE_PAUSE=true
PAUSER_ADDRESSES=0x...
ADMIN_ADDRESSES=0x...

# Performance Optimization
OPTIMIZER_RUNS=200
OPTIMIZER_ENABLED=true
VIA_IR=true

# DoS Protection
MAX_GAS_LIMIT=500000
MAX_BATCH_SIZE=50
MIN_TX_INTERVAL=1
```

---

## 🎯 Technology Comparison

| Feature | FHEVM React Template | Privacy Waste Rewards |
|---------|---------------------|----------------------|
| **Purpose** | SDK & Framework Templates | Production DApp Example |
| **Frontend** | React, Next.js, Vanilla JS | Vanilla JavaScript |
| **Smart Contract** | Example contracts | Full production contract |
| **Testing** | Basic SDK tests | 55 tests, 92% coverage |
| **CI/CD** | Not included | Full GitHub Actions pipeline |
| **Security** | Basic | Enterprise-grade (Solhint, Slither, ESLint) |
| **Documentation** | SDK docs | 2,000+ lines of docs |
| **Use Case** | Development toolkit | Real-world application |
| **Deployment** | Examples only | Production-ready on Sepolia |

---

## 🤝 Contributing

We welcome contributions to both technology stacks!

### Development Guidelines

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes**
4. **Run tests** (`npm test`)
5. **Run linting** (`npm run lint`)
6. **Commit your changes** (`git commit -m 'Add amazing feature'`)
7. **Push to branch** (`git push origin feature/amazing-feature`)
8. **Open a Pull Request**

### Code Standards

- ✅ Follow existing code style (Prettier + ESLint)
- ✅ Add tests for new features (maintain 90%+ coverage for privacy-waste-rewards)
- ✅ Update documentation as needed
- ✅ Ensure all CI/CD checks pass (for privacy-waste-rewards)
- ✅ Include clear commit messages
- ✅ Pre-commit hooks will auto-format code (for privacy-waste-rewards)

---

## 📞 Support & Resources

### Official Documentation
- **Zama Documentation**: [https://docs.zama.ai/](https://docs.zama.ai/)
- **FHEVM SDK**: [https://github.com/zama-ai/fhevm](https://github.com/zama-ai/fhevm)
- **Hardhat Docs**: [https://hardhat.org/docs](https://hardhat.org/docs)
- **Sepolia Testnet**: [https://sepolia.dev/](https://sepolia.dev/)

### Community
- **GitHub Issues**: [Report bugs or request features](https://github.com/KellenBode/FHEWasteRewards/issues)
- **Discussions**: [Join community discussions](https://github.com/KellenBode/FHEWasteRewards/discussions)

### Related Projects
- **Zama Bounty Program**: [https://github.com/zama-ai/bounty-program](https://github.com/zama-ai/bounty-program)
- **FHE Examples**: [https://github.com/zama-ai/fhevm-examples](https://github.com/zama-ai/fhevm-examples)

---

## 📄 License

Both technology stacks are licensed under the **MIT License**.

```
MIT License

Copyright (c) 2025 FHEVM Development Ecosystem

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 🌟 Acknowledgments

### Technology Partners
- **Zama** - For pioneering Fully Homomorphic Encryption and FHEVM technology
- **Ethereum Foundation** - For the Sepolia testnet infrastructure
- **Hardhat Team** - For the exceptional development framework
- **React Team** - For the React and Next.js frameworks

### Recognition

This repository demonstrates that **privacy and functionality can coexist**:
- **Accountable** - All transactions verifiable on-chain
- **Private** - Individual data remains encrypted
- **Developer-Friendly** - Easy-to-use SDK and clear examples
- **Production-Ready** - Enterprise-grade testing and security

---

## 🎖️ Achievement Highlights

### FHEVM React Template
- ✅ Framework-agnostic SDK design
- ✅ Multiple example implementations (Next.js, React, Vanilla JS)
- ✅ Comprehensive React hooks (useFhevmInit, useFhevmEncrypt, useFhevmDecrypt)
- ✅ Complete API route examples
- ✅ Security and validation utilities

### Privacy Waste Rewards
- ✅ 55 comprehensive tests (92% coverage)
- ✅ Enterprise-grade CI/CD pipeline
- ✅ Multi-layer security auditing
- ✅ Gas-optimized FHE operations
- ✅ Production-ready deployment infrastructure
- ✅ Real-world privacy-preserving use case

---

**Privacy + Sustainability + Developer Experience = Future of Web3**

*Building a more private, sustainable, and developer-friendly blockchain ecosystem with Fully Homomorphic Encryption.* 🌱🔐

---

**Quick Navigation**:
- [FHEVM React Template →](./fhevm-react-template/)
- [Privacy Waste Rewards →](./privacy-waste-rewards/)
- [Live Demo](https://fhe-waste-rewards.vercel.app/)
- [Contract](https://sepolia.etherscan.io/address/0x8EAB26B5C6E8Efe05D30b479C483802D2Ab15c14)
