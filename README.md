# Roomates Sheet (₨) 🏠

A production-ready, mobile-first roommate expense settlement web app tailored for flatmates and roommates managing shared living expenses with exact paisa precision, multi-user authentication, audit trails, and zero penny drift.

🌐 **Live Web App**: [https://sanaullahkhaan.github.io/roomates-sheet/](https://sanaullahkhaan.github.io/roomates-sheet/)  
📦 **GitHub Repository**: [https://github.com/Sanaullahkhaan/roomates-sheet](https://github.com/Sanaullahkhaan/roomates-sheet)

---

## 🚀 Key Features

### 🔐 1. Multi-User Authentication & Individual Accounts
* **Signup & Login**: Every roommate can create their own account with a username/email and password (hashed with SHA-256 via Web Crypto API).
* **Identity Attribution**: Transactions logged automatically record `by <User>` with timestamps.
* **1-Click Profile Switcher**: Easily switch between roommates on a shared household tablet or laptop.

### 🛡️ 2. Deletion History & Audit Trail (Zero Disputes)
* **Soft-Deletion Protection**: When any roommate deletes an expense or payment, it is **never permanently destroyed without a trace**.
* **Audit Tagging**: The audit log records **who deleted it**, **the exact date and time**, and the **original transaction details**.
* **1-Click Restore**: Any flatmate can inspect the `Audit (N)` log in the header and restore an accidentally or unfairly deleted transaction with 1 click.

### ⚖️ 3. Unequal & Custom Split Methods
* **Equally (=)**: Splits amount evenly with exact remainder paisa allocation so no penny is lost.
* **Exact Amounts (Rs.)**: Specify custom amounts per flatmate with live validation.
* **Shares / Weights (1x, 2x, etc.)**: Great for roommates who have guests or larger rooms.
* **Percentages (%)**: Specify custom percentage splits.

### 📊 4. Spending Analytics & Expense Categories
* **Categories**: 🛒 Groceries, ⚡ Electricity/Utilities, 🏠 Rent, 🍲 Food/Dining, 📶 Internet, 💧 Water, 🤝 Settlement, 📦 Other.
* **Visual Breakdown Bar**: Interactive category percentage and spend breakdown on the dashboard.
* **Category Filters**: Filter the transaction ledger by category with one tap.

### 🤝 5. 1-Click Fast Settlement Dialog
* Tap **"Settle Up"** on any settlement card on the dashboard.
* Choose payment method (💵 Cash, 📱 EasyPaisa, 📱 JazzCash, 🏦 Raast, 🏛️ Bank Transfer).
* Immediately records payment and updates balances without navigating away.

### 📥 6. Spreadsheet Export (Excel / CSV) & Backup
* **One-Click CSV Export**: Download a formatted `.csv` spreadsheet table with UTF-8 BOM encoding for seamless viewing in Microsoft Excel or Google Sheets.
* **JSON Backup & Restore**: Full local backup and restore capability.

### 📅 7. Monthly Billing Cycles
* Filter balances and ledger by month (e.g. `October 2026`, `All Time`) to isolate settlement cycles.

### 📱 8. Progressive Web App (PWA) Offline-First
* Includes `manifest.json` and `sw.js` (Service Worker).
* Roommates can tap **"Add to Home Screen"** on Chrome/Safari (Android/iOS) to install it like a native app.

---

## 📊 Benchmark Verification Suite

Dataset: 4 Roommates (`Sanaullah`, `Ahmed`, `Faizan`, `Ali`), 5 Shared Expenses (`Rs. 6,060.00`), 15 Direct Payments (`Rs. 8,730.00`).

### Expected & Verified Net Balances:
- **Faizan**: gets **+Rs. 2,580.84** (`+258,084` paisa)
- **Sanaullah**: gets **+Rs. 840.83** (`+84,083` paisa)
- **Ahmed**: owes **-Rs. 2,999.17** (`-299,917` paisa)
- **Ali**: owes **-Rs. 422.50** (`-42,250` paisa)
- **Net Sum**: **0.00 paisa** (Strict Zero-Sum Conservation)

### Optimal Greedy Settlement Transfers (3 Transactions):
1. **Ahmed** ➔ **Faizan**: **Rs. 2,580.84**
2. **Ali** ➔ **Sanaullah**: **Rs. 422.50**
3. **Ahmed** ➔ **Sanaullah**: **Rs. 418.33**
