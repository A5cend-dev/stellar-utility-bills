# stellar-utility-bills
Pay electricity, water, and internet bills instantly using Stellar assets
> Pay electricity, water, internet, and other utility bills using Stellar — instant settlement, minimal fees, global access.

![Stellar](https://img.shields.io/badge/Stellar-Network-blue?logo=stellar)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📌 Overview

Utility payments are a recurring pain point — long queues, failed transfers, and limited payment options. This app connects Stellar wallets directly to utility billing APIs, enabling one-tap payment for essential services.

### Key Features
- **Multi-Utility Support** — Electricity, water, internet, waste management
- **Bill Lookup by Account Number** — Fetch outstanding bills instantly
- **Scheduled Payments** — Auto-pay before due dates
- **Payment History & Receipts** — Full on-chain audit trail
- **Provider Integration Layer** — Pluggable API adapters for utility providers
- **Offline Queue** — Store failed payments and retry when network returns

---

## 📁 Folder Structure

```
stellar-utility-bills/
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── bills.js             # Bill lookup & payment
│   │   │   ├── providers.js         # Utility provider management
│   │   │   ├── transactions.js      # Payment history
│   │   │   └── scheduler.js        # Auto-pay logic
│   │   ├── services/
│   │   │   ├── stellarService.js
│   │   │   ├── billLookupService.js
│   │   │   └── providerService.js
│   │   ├── models/
│   │   │   ├── Bill.js
│   │   │   ├── Provider.js
│   │   │   ├── Payment.js
│   │   │   └── UserAccount.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   └── validate.js
│   │   └── integrations/
│   │       ├── electricityAdapter.js   # IKEDC, EKEDC, etc.
│   │       ├── waterAdapter.js
│   │       └── internetAdapter.js
│   └── config/
│       ├── stellar.js
│       └── providers.js
│
├── frontend/
│   └── src/
│       ├── components/
│       │   ├── BillCard/
│       │   ├── ProviderSelector/
│       │   ├── PaymentConfirm/
│       │   └── TransactionList/
│       ├── pages/
│       │   ├── Home.jsx
│       │   ├── PayBill.jsx
│       │   ├── History.jsx
│       │   └── AutoPay.jsx
│       ├── hooks/
│       │   ├── useBillLookup.js
│       │   └── useStellarPay.js
│       └── utils/
│           └── format.js
│
├── mobile/                          # React Native version
│   ├── screens/
│   ├── components/
│   └── navigation/
│
├── docs/
│   ├── PROVIDER_INTEGRATION.md      # How to add new utility providers
│   ├── API.md
│   └── DEPLOYMENT.md
│
└── tests/
```

---

## 🚀 Getting Started

```bash
git clone https://github.com/your-org/stellar-utility-bills.git
cd stellar-utility-bills
npm install && cp .env.example .env
npm run dev
```

---

## 🔌 Adding a Utility Provider

Implement the `ProviderAdapter` interface:

```javascript
class MyProviderAdapter {
  async lookupBill(accountNumber) { /* return bill details */ }
  async processPayment(bill, stellarTxHash) { /* confirm payment */ }
}
```

---

## 📄 License

MIT © 2025 — Built on the Stellar Network
