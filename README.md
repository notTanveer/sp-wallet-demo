# BOSS Summit - Silent Payment Wallet Workshop

## What is Silent Payments?

Silent Payments (BIP352) is a revolutionary Bitcoin protocol that enables receiving private payments from anyone using a single static address without requiring any interaction or extra on-chain overhead. Unlike traditional Bitcoin transactions that require communication between sender and receiver or leave privacy-compromising metadata, silent payments use static addresses that cannot be linked to actual payments on-chain.

**Key Features:**
- **Privacy by Default**: Transactions appear indistinguishable from regular Bitcoin transactions
- **No Address Reuse**: Every payment generates a unique on-chain address automatically
- **Static Payment Address**: Share one address, receive infinite payments privately
- **No Interaction Required**: Senders don't need to communicate with receivers
- **3 Tier Wallet Design**: Replaces traditional xpub/xpriv separation with Scan, Spend Keys, and Address components.

The protocol leverages elliptic curve Diffie-Hellman (ECDH) for key derivation, requiring recipients to scan the blockchain for payments. While scanning adds computational overhead, the privacy and usability benefits make it a game-changer for Bitcoin privacy.

## What We're Building

In this workshop, we'll demonstrate a **production-ready Silent Payment wallet** built on React Native, featuring:

- ✅ Full BIP352 implementation
- ✅ Mobile-first architecture (iOS & Android)
- ✅ Efficient blockchain scanning with indexer integration
- ✅ Real-time payment detection
- ✅ Transaction history and UTXO management
- ✅ Wallet Birth height optimization for faster syncing

## Timeline

| Topic                                    | Duration (min) | Format       | Host            |
| ---------------------------------------- | -------------- | ------------ | --------------- |
| Introduction to Silent Payments          | 20             | Presentation | TBD             |
| Silent Payment Wallet Architecture       | 15             | Presentation | TBD             |
| Live Demo: Create & Fund Wallet          | 30             | Live Demo    | TBD             |
| Challenge: Sweep the Wallet!             | 45             | Interactive  | TBD             |
| Architecture Deep Dive                   | 20             | Discussion   | TBD             |
| Q&A and Wrap-up                          | 10             | Discussion   | All             |

## Workshop Flow

### Part 1: Live Demonstration (30 minutes)

**What we'll do:**

1. **Create a Fresh Wallet** 🆕
   - Generate a new Silent Payment wallet live on stage
   - Show the Silent Payment address (sp1...)
   - Explain the address format and structure

2. **Fund the Wallet** 💸
   - Send Bitcoin to the wallet's silent payment address from a test wallet
   - Broadcast the transaction on testnet/signet
   - Wait for confirmation

3. **Detect the Payment** 🔍
   - Watch as the wallet scans and detects the incoming payment
   - Show real-time scanning progress
   - Display the detected UTXO with transaction details

4. **Make Seed Public** 🔓
   - Reveal the mnemonic seed phrase to everyone
   - Display it on the big screen
   - Share via QR code

### Part 2: Interactive Challenge (45 minutes)

TODO: update challenge

**The Challenge: First Come, First Served!** 🏆

Once the seed is public, participants will:

1. **Download the Wallet App**
   - iOS: TestFlight link (TODO: provide link)
   - Android: APK download link (TODO: provide link)

2. **Import the Wallet**
   - Use the shared seed phrase
   - Let it sync and detect the UTXOs

3. **Race to Withdraw!**
   - First person to successfully sweep the funds wins
   - Learn about:
     - Wallet import/recovery
     - UTXO scanning
     - Transaction creation
     - Fee management
     - Race conditions in Bitcoin

**Learning Objectives:**
- Hands-on experience with Silent Payment wallet recovery
- Understanding blockchain scanning requirements
- Real-world transaction broadcasting
- Dealing with concurrent spends and UTXO conflicts

## Workshop Prerequisites

### Required Software

1. **For Mobile Testing:**
   - iOS: iPhone with iOS 15+ and TestFlight app installed
   - Android: Android device with Android 11+ (TODO: insert apk/zip file)

2. **For Local Development (Optional):**
   - Node.js v18+ ([download](https://nodejs.org/))
   - Xcode (Mac only, for iOS development)
   - Android Studio (for Android development)


**For Challenge Participants (Recommended):**
- JUST BRING YOUR PHONE
- We'll provide download links during the workshop

## Technical Architecture Overview

### Key Components

1. **BIP352 Core Implementation**
   - Pure TypeScript implementation
   - ECDH-based output scanning
   - Label support (future)

2. **Blockchain Scanning**
   - Indexer-based architecture (not full node required)
   - Efficient backward scanning (latest blocks first)
   - Birth height optimization
   - Incremental scanning with checkpoints

3. **UTXO Management**
   - Persistent storage (not re-fetchable like regular wallets)
   - Spent status tracking
   - Tweak data preservation for spending

4. **Mobile Optimizations**
   - Background scanning
   - Progress indicators
   - Efficient memory usage
   - React Native performance optimizations`

## Additional Reading Materials

### Essential Resources

- **Official Specification**: [BIP352](https://github.com/bitcoin/bips/blob/master/bip-0352.mediawiki)
- **Silent Payments Website**: [silentpayments.xyz](https://silentpayments.xyz)
- **Original Proposal**: [Ruben Somsen's gist](https://gist.github.com/RubenSomsen/c43b79517e7cb701ebf77eec6dbb46b8)

### Blog Posts & Guides

- **Bitcoin Optech**: [Silent Payments Topic](https://bitcoinops.org/en/topics/silent-payments/)
- **Area Bitcoin**: [Silent Payments Blog](https://blog.areabitcoin.co/silent-payments/)
- **BitBox Series**:
  - [Part 1: Understanding Silent Payments](https://bitbox.swiss/blog/understanding-silent-payments-part-one/)
  - [Part 2: Technical Deep Dive](https://bitbox.swiss/blog/understanding-silent-payments-part-two/)

### Implementation References

- **This Project**: [Silent Payment Wallet GitHub](https://github.com/Bitshala-Incubator/silent-pay-wallet)
- **Core Library**: [@silent-pay/core](https://github.com/Bitshala-Incubator/silent-pay)
- **Indexer**: [Silent Payment Indexer](https://github.com/Bitshala-Incubator/silent-pay-indexer)

## Post-Workshop Discussion Topics

### Mobile Wallet Integration Challenges

**Topics to Explore:**

1. **Scanning Efficiency**
   - How can we make scanning faster on mobile?
   - Trade-offs between privacy and performance
   - Indexer architecture vs. direct node connection
   - Bandwidth optimization for mobile networks

2. **Battery & Resource Management**
   - Background scanning strategies
   - Balancing scan frequency with battery life
   - Memory constraints on mobile devices
   - Handling app suspension/termination

3. **User Experience**
   - First-sync experience (scanning from wallet birthday)
   - Progress indicators and time estimates
   - Handling network interruptions
   - Wallet backup and recovery flow

### Hardware Wallet Integration

**Topics to Explore:**

1. **Key Management**
   - How to derive Silent Payment keys on hardware wallets?
   - Scan key exposure for light clients
   - Secure spending key isolation

2. **Signing Flow**
   - PSBT modifications for Silent Payments - [BIP-375](https://github.com/bitcoin/bips/blob/master/bip-0375.mediawiki)
   - Computing tweaks on hardware devices
   - Verification and confirmation UX

3. **Implementation Challenges**
   - Firmware limitations
   - Screen real estate for displaying SP addresses
   - Compatibility with existing standards

### Scaling & Optimization

**Topics to Explore:**

1. **Indexer Architecture**
   - Centralized vs. distributed indexers
   - Trust assumptions
   - Self-hosted indexer options

2. **Light Client Solutions**
   - BIP157/158 (compact block filters) integration
   - Privacy-preserving filter download
   - Client-side scanning optimization

3. **Future Protocol Improvements**
   - BIP352 label support
   - Output linking prevention
   - Cross-wallet compatibility

## Expected Outcomes

By the end of this workshop, participants will:

✅ **Understand** Silent Payments protocol fundamentals  
✅ **Experience** using a Silent Payment wallet hands-on  
✅ **Learn** about blockchain scanning requirements  
✅ **Identify** practical challenges in mobile wallet development  
✅ **Contribute** ideas for improving Silent Payment adoption  
✅ **Network** with other Bitcoin developers working on privacy  

## Get Involved

### Contribute to the Project

- **GitHub**: [silent-pay-wallet](https://github.com/Bitshala-Incubator/silent-pay-wallet)
- **Issues**: Report bugs or suggest features
- **Pull Requests**: Code contributions welcome!

### Join the Community

- **Bitshala Discord**: [Join here](https://discord.gg/DETyMZj24H)
- **Follow Updates**: [@tanveer](https://twitter.com/tnvvrrr) | [@theanmolsharma_](https://twitter.com/theanmolsharma_) | [@Chaitika_](https://x.com/Chaitika_)

### What's Next?

After the workshop, we'll share:
- Full source code walkthrough video
- Architecture documentation
- Testing guide
- Deployment instructions for your own indexer

---

**Let's build a more private Bitcoin together! 🚀**
