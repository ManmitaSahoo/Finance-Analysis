# Finance-Analysis
This project builds a **credit scoring system** for wallets interacting with Aave V2 on the Polygon network.  
It evaluates each wallet's historical DeFi activity and generates a score between **0 and 1000**, reflecting the financial behavior and reliability of the user.

---

## 📁 Project Files

| File                         | Description |
|------------------------------|-------------|
| `try1.ipynb`                 | Main Jupyter notebook with full data pipeline |
| `user-wallet-transactions.json` | Raw input data of wallet transactions |
| `wallet_features.csv`        | Extracted behavior metrics for each wallet |
| `wallet_scores.csv`          | Final credit scores |

## 🧾 Data Source

- Dataset: `user-wallet-transactions.json`
- Format: JSON list of wallet transaction records
- Example entry:

```json
{
  "userWallet": "0x000...b6d4b6",
  "network": "polygon",
  "protocol": "aave_v2",
  "action": "deposit",
  "actionData": {
    "amount": "2000000000",
    "asset": "0x...address"
  },
  ...
}

The scoring logic gives:

> Higher scores to wallets with:
High deposits
Frequent repayments
Low liquidation rate
Responsible borrowing ratios

> Lower scores to wallets with:
High borrow-to-deposit ratio
Frequent liquidations
Low repayment behavior
