# BOSS Summit - Silent Payment Wallet Workshop

<div align="center">
  <img src="assets/shroud.png" alt="Shroud Wallet Logo" width="200"/>
</div>

## Synopsis: What is this workshop?

This workshop demonstrates **Shroud** - a **Silent Payment wallet** built on React Native. Silent Payments (BIP352) is a revolutionary Bitcoin protocol that enables receiving private payments from anyone using a single static address without requiring any interaction or extra on-chain overhead.

We'll walk through creating a Shroud wallet live, funding it, and then challenge participants to be the first to sweep the funds by importing the wallet on their mobile devices. This hands-on experience will teach you about Silent Payments implementation, blockchain scanning, and real-world Bitcoin transactions.

**Key Features of Silent Payments:**
- **Privacy by Default**: Transactions appear indistinguishable from regular Bitcoin transactions
- **No Address Reuse**: Every payment generates a unique on-chain address automatically
- **Static Payment Address**: Share one address, receive infinite payments privately
- **No Interaction Required**: Senders don't need to communicate with receivers

## Timeline

| Topic                                    | Duration (min) | Format       | Host            |
| ---------------------------------------- | -------------- | ------------ | --------------- |
| Introduction and Silent Payments 101     | 20             | Presentation | TBD             |
|  Wallet Architecture                     | 15             | Presentation | TBD             |
| Live Demo: Create & Fund Wallet          | 30             | Live Demo    | TBD             |
| Challenge: Sweep the Wallet!             | 45             | Interactive  | TBD             |
| Problem Discussion: HWW Support,Fast Scan| 20             | Discussion   | TBD             |
| Q&A and Wrap-up                          | 10             | Discussion   | All             |

### Activity Breakdown

**Part 1: Live Demonstration (30 minutes)**
1. Create a fresh Silent Payment wallet on stage
2. Fund the wallet by broadcasting a transaction
3. Watch real-time scanning and payment detection
4. Reveal the seed phrase publicly

**Part 2: Interactive Challenge (45 minutes)**
- Participants download Shroud (Android)
- Import the shared seed phrase
- Race to be the first to sweep the funds!
- Learn about UTXO scanning, transaction creation, and race conditions

## Prerequisites

### Required Software

**For Challenge Participants:**
- Android: Android device with Android 11+
- **JUST BRING YOUR PHONE** - We'll provide download links during the workshop

### Platform support

- Android only: please bring an Android device running Android 11 or later. We'll provide the APK or Play Store link during the workshop.
- iOS is not supported for the live challenge — App Store registration and review timelines add unpredictable delays, so iOS builds won't be available for on-stage imports. iOS users can follow the repo/Discord for post-workshop builds or use an Android emulator.

**For Local Development (Optional):**
- Node.js v18+ ([download](https://nodejs.org/))
- Xcode & Android Studio ([Build and Run it](https://github.com/Bitshala-Incubator/silent-pay-wallet?tab=readme-ov-file#build--run-it))

## Major Problem Statements

### Mobile Wallet Integration Challenges

1. **Scanning Efficiency**
   - How can we make scanning faster on mobile?
   - Trade-offs between privacy and performance
   - Indexer architecture vs. direct node connection

2. **Battery & Resource Management**
   - Background scanning strategies
   - Memory constraints on mobile devices
   - Handling app suspension/termination

3. **User Experience**
   - First-sync experience (scanning from wallet birthday)
   - Progress indicators and time estimates
   - Wallet backup and recovery flow

### Hardware Wallet Integration

1. **Key Management**
   - How to derive Silent Payment keys on hardware wallets?
   - Scan key exposure for light clients
   - Secure spending key isolation

2. **Signing Flow**
   - PSBT modifications for Silent Payments - [BIP-375](https://github.com/bitcoin/bips/blob/master/bip-0375.mediawiki)
   - Computing tweaks on hardware devices
   - Verification and confirmation UX

### Scaling & Optimization

1. **Indexer Architecture**
   - Centralized vs. distributed indexers
   - Trust assumptions and self-hosted options

2. **Light Client Solutions**
   - BIP157/158 (compact block filters) integration
   - Privacy-preserving filter download
   - Client-side scanning optimization

## Main Takeaways

By the end of this workshop, participants will:

✅ **Understand** Silent Payments protocol fundamentals and BIP352  
✅ **Experience** using Shroud wallet hands-on  
✅ **Learn** about blockchain scanning requirements and UTXO management  
✅ **Identify** practical challenges in mobile wallet development  
✅ **Contribute** ideas for improving Silent Payment adoption  
✅ **Network** with other Bitcoin developers working on privacy  

---

## Additional Resources

### Essential Reading

- **Official Specification**: [BIP352](https://github.com/bitcoin/bips/blob/master/bip-0352.mediawiki)
- **Silent Payments Website**: [silentpayments.xyz](https://silentpayments.xyz)
- **Bitcoin Optech**: [Silent Payments Topic](https://bitcoinops.org/en/topics/silent-payments/)

### Implementation References

- **Shroud Wallet**: [Silent Payment Wallet GitHub](https://github.com/Bitshala-Incubator/silent-pay-wallet)
- **Core Library**: [@silent-pay/core](https://github.com/Bitshala-Incubator/silent-pay)
- **Indexer**: [Silent Payment Indexer](https://github.com/Bitshala-Incubator/silent-pay-indexer)

## Get Involved

- **GitHub**: [silent-pay-wallet](https://github.com/Bitshala-Incubator/silent-pay-wallet)
- **Bitshala Discord**: [Join here](https://discord.gg/DETyMZj24H)
- **Follow Updates**: [@tanveer](https://twitter.com/tnvvrrr) | [@theanmolsharma_](https://twitter.com/theanmolsharma_) | [@Chaitika_](https://x.com/Chaitika_)

---

**Let's build a more private Bitcoin together! 🚀**