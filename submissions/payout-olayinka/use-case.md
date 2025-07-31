---
title: "Real-World Use Case---

## 💡 Solution: Chim**Challenge:**
- Creators in Ghana, Nigeria, and Uganda often lacked access to bank accounts.
- Creativo faced high costs and delays in settling international payouts.

**Solution:**
- Creativo integrated Chimoney's Interledger payout API.
- After a creator makes a sale, Creativo calls the API with the wallet address and amount.
- Creators receive money instantly in their Interledger wallet, and can withdraw via mobile money, airtime, or gift cards.ayout to Interledger Wallet Address API

Using Chimoney's `payouts/interledger/wallet-address` endpoint, platforms can:ayout to Interledger Wallet Address"
endpoint: "payout"
author: "Olayinka"
date: "2025-01-26"
description: "A practical scenario demonstrating the utility of Chimoney's Payout to Interledger Wallet Address API"
---


# Use Case: Enabling Global Creator Payouts via Interledger Wallets Using Chimoney

---

## 🚩 Problem

The creator economy is booming — from YouTubers and TikTokers to online teachers and freelance writers. But paying creators globally remains a major barrier, especially for startups or creator-focused platforms in emerging markets.

- Bank transfers are slow, expensive, and often limited by currency issues.
- Platforms struggle to integrate multiple financial services for global reach.
- Many creators don't have access to traditional bank accounts — but they do have access to digital wallets or crypto rails like Interledger.

---

## 🎯 Target Audience

- Creator-focused platforms (e.g., e-learning sites, freelance marketplaces)
- Fintechs managing cross-border payments
- Web3 apps needing fiat-compatible wallet payouts
- Payment aggregators & global talent marketplaces

These businesses need an **API-first**, **borderless**, and **currency-flexible** solution to pay global users instantly.

## Solution: Chimoney’s Payout to Interledger Wallet Address API

Using Chimoney’s `payouts/interledger/wallet-address` endpoint, platforms can:

- Send money in supported currencies (e.g., USD, NGN) directly to a user’s Interledger-compatible wallet
- Integrate in minutes using a simple POST request
- Track transactions with a `transactionRef` in the response
- Scale globally without worrying about banking restrictions

### What Is Interledger?

The Interledger Protocol (ILP) is an open payments network that allows money to move instantly and securely between different wallets, banks, and payment systems — just like how the internet routes data.

By leveraging Interledger, Chimoney empowers platforms to send payouts without building complex infrastructure or handling currency conversions directly.

---

## 🌍 Real-World Example

### Startup: Creativo

> Creativo is a Kenyan-based platform helping African creators monetize digital content like courses, templates, and videos.

Challenge:
- Creators in Ghana, Nigeria, and Uganda often lacked access to bank accounts.
- Creativo faced high costs and delays in settling international payouts.

Solution:
- Creativo integrated Chimoney’s Interledger payout API.
- After a creator makes a sale, Creativo calls the API with the wallet address and amount.
- Creators receive money instantly in their Interledger wallet, and can withdraw via mobile money, airtime, or gift cards.

---

## 🔄 Process Flow

1. Creator completes a task or earns revenue.
2. Platform checks balance and initiates a payout.
3. Platform sends a POST request to Chimoney with:
   - wallet address
   - amount
   - currency (e.g., USD)
   - wallet provider (e.g., Rafiki)
4. Chimoney confirms with a `transactionRef` and the creator is notified.

```text
[Platform] → [Chimoney API] → [Interledger Wallet] → [Creator Gets Paid]
Benefits
```

---

## ✅ Benefits

- **Speed**: Funds delivered instantly
- **Scalability**: One API works globally
- **Inclusion**: Reaches the unbanked or underbanked creators
- **Security**: Secure, token-authenticated API
- **Cost-effective**: No need for international banking contracts

---

## 📋 Supporting Considerations

- Requires secure API key for authentication
- Scales well with batch operations and creator platforms
- Supports multiple wallet providers via Interledger
- Can be tested in dev environments before live deployment

---

## 📘 Next Steps

Ready to build it? Check the tutorial for a hands-on guide or follow the setup guide to test your first payout.