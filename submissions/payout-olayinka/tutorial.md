---
title: "Complete Tutorial: Sending Money to Interledger Wallets with Chimoney"
endpoint: "payouts/interledger/wallet-address"
author: "Olayinka"
date: "2025-07-31"
description: "Master Chimoney's Interledger payout API with practical examples and real implementations"
difficulty: "Beginner to Expert"
estimated_time: "15-20 minutes"
---

# Tutorial: Sending Money to an Interledger Wallet with Chimoney

> **The Future of Cross-Border Payments**: Learn how to leverage Chimoney's powerful Interledger integration for seamless, instant global payouts.

This comprehensive tutorial walks you through using Chimoney's `payouts/interledger/wallet-address` endpoint to send payouts directly to Interledger-compatible wallets. We'll cover everything from basic authentication to advanced error handling.

## 🎯 What You'll Accomplish

By completing this tutorial, you'll master:
- ✅ **Authentication** with Chimoney using your API key
- ✅ **Request Construction** with proper payload formatting
- ✅ **API Integration** using multiple tools (curl, Postman, JavaScript)
- ✅ **Response Handling** and error management
- ✅ **Best Practices** for production implementations

### � Real-World Scenario
**Goal**: Send a $25 payout in USD to a creator's Interledger wallet address using Chimoney's secure API.

---

## �️ Prerequisites & Setup

### Required Accounts & Tools
- ✅ **Chimoney Developer Account** → [https://chimoney.io](https://chimoney.io)
- ✅ **Dashboard Access** with verified email
- ✅ **API Key** (found in your dashboard after signing up)
- ✅ **Test Interledger Wallet** (you can use demo: `ilp:test.wallet`)

### Choose Your Testing Tool
Pick one of these REST clients:
- 🚀 **[Postman](https://www.postman.com/)** (Recommended for beginners)
- ⚡ **[Hoppscotch](https://hoppscotch.io/)** (Web-based alternative)
- 💻 **Terminal with `curl`** (For command-line enthusiasts)

### 🔍 Quick Environment Check
Before we start, verify you have:
```bash
# Test your curl installation
curl --version

# Test internet connectivity to Chimoney
curl -I https://api.chimoney.io
```

---

## 1️⃣ Step 1: Set Up Your Authorization

All Chimoney API requests require **Bearer Token authentication**.

### Example Header:
```
Authorization: Bearer YOUR_API_KEY
```

Include this in every API request.

---

## 2️⃣ Step 2: Construct the Payout Request

### Endpoint:
```
POST https://api.chimoney.io/v0.2.4/payouts/interledger/wallet-address
```

### Required Payload Parameters:
| Key             | Type   | Description                              |
|------------------|--------|------------------------------------------|
| `walletAddress`  | string | The Interledger wallet address of user   |
| `walletProvider` | string | The wallet provider (e.g., `rafiki`)     |
| `amount`         | number | Amount to send                           |
| `currency`       | string | Supported currency code (e.g., `USD`)    |

---

## 3️⃣ Step 3: Sample Request with `curl`

```bash
curl -X POST https://api.chimoney.io/v0.2.4/payouts/interledger/wallet-address \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "walletAddress": "ilp:test.wallet",
    "walletProvider": "rafiki",
    "amount": 25,
    "currency": "USD"
  }'
```

---

## 4️⃣ Step 4: Example Postman Setup

**Method:** POST  
**URL:** https://api.chimoney.io/v0.2.4/payouts/interledger/wallet-address

### Headers:
| Key              | Value                    |
|------------------|--------------------------|
| Authorization    | Bearer YOUR_API_KEY      |
| Content-Type     | application/json         |

### Body (JSON):
```json
{
  "walletAddress": "ilp:test.wallet",
  "walletProvider": "rafiki",
  "amount": 25,
  "currency": "USD"
}
```

---

## ✅ Expected Successful Response

```json
{
  "status": "success",
  "message": "Interledger wallet payout initiated",
  "data": {
    "transactionRef": "ref_123456789"
  }
}
```

---

## ❌ Common Errors

| Error                     | Cause                           | Fix                                    |
|---------------------------|---------------------------------|----------------------------------------|
| 401 Unauthorized          | Invalid or missing API key      | Check your API key, use Bearer format |
| 400 Bad Request           | Missing or invalid payload      | Make sure all required fields are included |
| 500 Internal Server Error | Server-side issue               | Try again or contact support           |

---

## ✅ Final Notes

You can test in Postman with dummy wallet addresses.

Always store your transactionRef for tracking or auditing.

For production, integrate this into your backend code using a language like Node.js, Python, or PHP.

