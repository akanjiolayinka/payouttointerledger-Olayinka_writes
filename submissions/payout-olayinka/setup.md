---
title: "Setup Guide: Getting Started with Chimoney Payout API"
endpoint: "payout"
author: "Olayinka"
date: "2025-01-26"
description: "Complete s---

## 🏁 Final Checklist

✅ API key securely added  
✅ Base URL and endpoint configured  
✅ Request body formatted correctly  
✅ Headers included  
✅ Request tested and working in Postman or curl

---

## 🧩 Next Steps

You're ready to build your own payout integration!  
Continue to the tutorial.md guide to see how to integrate this endpoint into a real-world use case. for authentication, API keys, and making your first API call"
difficulty: "Beginner"
---


# Setup Guide: Get Started with Chimoney Interledger Payouts API

This guide walks you through how to authenticate and prepare your development environment so you can successfully call the Chimoney `payouts/interledger/wallet-address` endpoint.

Whether you’re a beginner or pro, this guide ensures you can send your first payout confidently.

---

## 🎯 What You’ll Set Up

By the end of this guide, you'll have:
- A working Chimoney Developer account
- Your API key ready
- Your environment configured to test the payout API
- A successful request sent to an Interledger wallet

---

## 🧰 Prerequisites

Before you start, make sure you have:

- ✅ A Chimoney Developer Account → [https://chimoney.io](https://chimoney.io)
- ✅ API Key (get it from your Chimoney dashboard)
- ✅ A test Interledger wallet address (e.g., `ilp:test.wallet`)
- ✅ A REST API testing tool:
  - [Postman](https://www.postman.com/)
  - [Hoppscotch](https://hoppscotch.io/)
  - or `curl` on your terminal

---

## 🗝️ Step 1: Get Your API Key

1. Go to [https://chimoney.io](https://chimoney.io)
2. Log in or sign up for a developer account.
3. Go to the **Dashboard**
4. Navigate to the **API Keys** section
5. Copy your API key (keep it secure)

---

## 🔐 Step 2: Set Up Authentication

All Chimoney APIs require **Bearer token authentication**.

### Example Header:
```
Authorization: Bearer YOUR_API_KEY
```

Replace `YOUR_API_KEY` with the API key from your dashboard.

> 🔒 Never expose your API key in public code repositories or frontend apps.

---

## 🌍 Step 3: Base URL and Endpoint

- **Base URL**: `https://api.chimoney.io`
- **Full Endpoint**:  
```
POST /v0.2.4/payouts/interledger/wallet-address
```

---

## 📦 Step 4: Payload Format

Here’s the format of the JSON body you'll send with your request:

```json
{
  "walletAddress": "ilp:test.wallet",
  "walletProvider": "rafiki",
  "amount": 25,
  "currency": "USD"
}
```

| Field            | Required | Description                              |
|------------------|----------|------------------------------------------|
| walletAddress    | ✅       | Interledger-compatible wallet address   |
| walletProvider   | ✅       | Provider name (e.g., rafiki)            |
| amount           | ✅       | Amount to send                           |
| currency         | ✅       | ISO currency code like USD, NGN, etc.   |

---

## 🧪 Step 5: Test with Postman
Here’s how to test the endpoint in Postman:

1. Create a new POST request
URL:

bash
Copy
Edit
https://api.chimoney.io/v0.2.4/payouts/interledger/wallet-address
2. Set Headers:
Key	Value
Authorization	Bearer YOUR_API_KEY
Content-Type	application/json

3. Add Body (raw JSON):
json
Copy
Edit
{
  "walletAddress": "ilp:test.wallet",
  "walletProvider": "rafiki",
  "amount": 25,
  "currency": "USD"
}
### 4. Click Send

---

## ✅ Step 6: Verify Success
If your setup is correct, you should receive a response like this:

```json
{
  "status": "success",
  "message": "Interledger wallet payout initiated",
  "data": {
    "transactionRef": "ref_123456789"
  }
}
```

This means your payout has been successfully initiated!

---

## ❗ Troubleshooting Common Errors

| Status Code | Error Message           | Possible Fix                                    |
|-------------|-------------------------|-------------------------------------------------|
| 401         | Unauthorized            | Check your API key and Authorization header    |
| 400         | Bad Request             | Make sure all fields are present and valid     |
| 500         | Internal Server Error   | Try again later or contact Chimoney support    |

🏁 Final Checklist
✅ API key securely added
✅ Base URL and endpoint configured
✅ Request body formatted correctly
✅ Headers included
✅ Request tested and working in Postman or curl

🧩 Next Steps
You’re ready to build your own payout integration!
Continue to the tutorial.md guide to see how to integrate this endpoint into a real-world use case.
