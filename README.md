# 🔎 Cryptocurrency Forensics Assessment (Challenge 2 – Task 1 & Task 2)
### Written by GPT-4.1

This repository contains the solution for **Challenge 2: Data Science (Cryptocurrency) Assessment**  
from the **Digital Forensics Internship – Take Home Assessment**.

It includes two tasks:

- **Task 1** → Ethereum wallet transaction analysis (Etherscan API + Network Graph)  
- **Task 2** → Token-level forensic analysis of market anomalies (CoinGecko API + anomaly detection)

---

## 📖 Task Description (from Assessment PDF)

### **Task One**  
- Use a public blockchain API (e.g. Etherscan or Blockchain.com) to:  
  1. Query recent transactions of a crypto wallet address (chosen by user).  
  2. Plot a simple graph:  
     - **Nodes** = Wallet addresses  
     - **Edges** = Transactions  
  3. Focus on a small subset (e.g. 10–20 transactions) for clarity.  

**Bonus**  
- Provide insights on wallet activity and possible illicit activity (e.g., high-value transfers, self-transfers).

---

### **Task Two**  
- Perform basic forensic analysis on a token of your choice where a period (7–30 days) shows unusual market activity (e.g., pump-and-dump).  
- Highlight suspicious movements.  
- Output can include:  
  - Time series with anomalies  
  - Histograms of transaction sizes or times  
  - Annotated charts with suspicious activity  

---

## 🚀 Features Implemented

### **Task 1 – Wallet Graph**
- Fetches up to N recent transactions for any Ethereum wallet via **Etherscan**.  
- Builds a **directed transaction graph** (sender → receiver).  
- Visualizes graph with **NetworkX + Matplotlib**.  
- Detects suspicious activity:  
  - **High-value transactions** (custom ETH threshold).  
  - **Self-transfers**.  
- Suspicious edges are highlighted in **red**.  
- Results printed in a simple log.

### **Task 2 – Token Analysis**
- Uses **CoinGecko API** for token price & volume history.  
- Detects anomalies using **volume spike detection**.  
- Outputs:  
  - Time series plots with anomaly markers.  
  - Histogram of trading volumes with anomaly threshold.  
- Suspicious activity printed in the same style as Task 1 (`suspicious detect / less sus`).  

---

## 📂 Project Structure

```

TASK1.ipynb   # Ethereum wallet transaction graph (Task 1)
TASK2.ipynb   # Token market anomaly detection (Task 2)
README.md     # Documentation (this file)
requirements.txt  # Dependencies
.env.example  # Template for API keys

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

### 4. Configure API keys

* For **Task 1 (Etherscan)**, add your API key to `.env`:

  ```
  etherscankey=YOUR_ETHERSCAN_API_KEY
  ```
* For **Task 2 (CoinGecko)**, **no API key is required**.

---

## ▶️ Usage

### **Task 1**

```bash
jupyter notebook TASK1.ipynb
```

* Set the wallet address:

  ```python
  wallet_address = "0xd8dA6BF26964aF9D7eEd9e03E53415D37aA96045"  # Example: Vitalik Buterin
  ```
* Run all cells to:

  * Fetch transactions
  * Build transaction graph
  * Get suspicious activity report

---

### **Task 2**

```bash
jupyter notebook TASK2.ipynb
```

* Set the token ID (CoinGecko format):

  ```python
  df = get_token_market_data("shiba-inu", days=30)
  ```
* Run all cells to:

  * Fetch historical market data
  * Detect anomalies in trading volume
  * Visualize time series & histograms
  * Print suspicious activity report

---

## 📊 Example Results

### **Task 1 – Suspicious Transactions**

```text
suspicious detect:
- 0xabc123... | 0xWallet1 → 0xWallet2 | 150.00 ETH | Reason: High value
- 0xdef456... | 0xWallet3 → 0xWallet3 | 10.00 ETH  | Reason: Self-transfer
```

Or, if no issues:

```text
less sus
```

---

### **Task 2 – Token Market Analysis**

* **Volume Time Series**
  ![volume-example](docs/example_volume.png)

* **Suspicious Output**

  ```text
  suspicious detect:
  - 2025-08-21 14:00:00 | Volume: 2,310,000,000 USD | Reason: Volume spike
  ```

Or:

```text
less sus
```

---

## ✅ Deliverables (as per PDF)

* **Source code**: Jupyter notebooks for Task 1 and Task 2.
* **Documentation**: This README.
* **Setup instructions**: Included.
* **Results**: Graphs & suspicious transaction/market logs.
