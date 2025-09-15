# 🔎 Ethereum Wallet Transaction Analysis (Challenge 2 – Task 1)
### Written by GPT-4.1

This repository contains the solution for **Challenge 2: Data Science (Cryptocurrency) Assessment – Task 1**  
from the **Digital Forensics Internship – Take Home Assessment**.

The project demonstrates how to:
- Fetch recent transactions of an Ethereum wallet address using **Etherscan API**.
- Build and visualize a simple **graph of transactions**.
- Perform **basic forensic analysis** to detect possible anomalies or illicit activity.

---

## 📖 Task Description (from Assessment PDF)

**Task One**  
- Use a public blockchain API (e.g. Etherscan or Blockchain.com) to:  
  1. Query recent transactions of a crypto wallet address (chosen by user).  
  2. Plot a simple graph:  
     - **Nodes** = Wallet addresses  
     - **Edges** = Transactions  
  3. Focus on a small subset (e.g. 10–20 transactions) for clarity.  

**Bonus**  
- Provide insights on wallet activity and possible illicit activity (e.g., high-value transfers, self-transfers).

---

## 🚀 Features Implemented

- Fetches up to N recent transactions for any Ethereum wallet via **Etherscan**.  
- Builds a **directed transaction graph** (sender → receiver).  
- Visualizes graph with **NetworkX + Matplotlib**.  
- **Bonus forensic analysis**:  
  - Flags **high-value transactions** (user-defined ETH threshold).  
  - Flags **self-transfers**.  
  - Highlights suspicious edges in **red**.  
  - Prints a log of suspicious transactions in a concise format.

---

## 📂 Project Structure

```

TASK1.ipynb   # Jupyter notebook with step-by-step solution
README.md                         # Documentation (this file)
requirements.txt                  # Dependencies

````

---

## 🔧 Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/Samuel-Kong/cryptocurrency-assessment.git
cd cryptocurrency-assessment
````

### 2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API key

* Add your **Etherscan API key** to .env:

  ```
  etherscankey=YOUR_ETHERSCAN_API_KEY
  ```

---

## ▶️ Usage

1. Open the notebook:

   ```bash
   jupyter notebook TASK1.ipynb
   ```

2. In the notebook, set the wallet address:

   ```python
   wallet_address = "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045"  # Example: Vitalik Buterin
   ```

3. Run all cells to:

   * Fetch transactions
   * Build the transaction graph
   * Visualize interactions
   * Get suspicious activity report

---

## 📊 Example Results

* **Transaction Graph**
  (Wallet addresses as nodes, transactions as edges)
  ![graph-example](docs/example_graph.png)

* **Suspicious Transactions Output**

  ```text
  suspicious detect:
  - 0xabc123... | 0xWallet1 → 0xWallet2 | 150.00 ETH | Reason: High value
  - 0xdef456... | 0xWallet3 → 0xWallet3 | 10.00 ETH  | Reason: Self-transfer
  ```

  Or, if no issues are found:

  ```text
  less sus
  ```

---

## ✅ Deliverables (as per PDF)

* **Source code**: Provided in Jupyter Notebook.
* **Documentation**: This README.
* **Setup instructions**: Included.
* **Results**: Graphs & suspicious transaction logs.
