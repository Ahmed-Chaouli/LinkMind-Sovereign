# 🛡️ LinkMind Sovereign

**An Advanced Network Automation Tool for Huawei NCE Transmission Optimization.**

LinkMind Sovereign is a Python-based engine designed for Telecom Transmission Engineers. It automates the critical process of reclaiming wasted bandwidth resources (E1/TDM) from Hybrid Microwave Links and repurposing them for Ethernet traffic.

## 🚀 Key Features

* **Intelligent Reclamation:** Identifies unused E1s and calculates the exact capacity to be freed.
* **Dual-Script Generation:** Automatically generates two MML scripts simultaneously:
    * `EXECUTE_PLAN.mml`: To perform the deletion and capacity shrinking.
    * `ROLLBACK_PLAN.mml`: To reverse all changes and restore services in case of emergencies.
* **Hybrid Microwave Support:** Specifically targets `CFG-IFPORT-HYBRID` commands to optimize the split between TDM and Packet planes.
* **Safety First:** Implements a "Deactivate -> Delete" logic to prevent ghost trails.

## 🛠️ How It Works

1.  **Input:** Takes an Excel sheet containing analyzed network data (Service IDs, Slot/Port, Wasted Capacity).
2.  **Processing:**
    * Validates the input data.
    * Calculates the new `E1CAPACITY` for the IF board.
    * Constructs the MML commands for Huawei RTN/OSN equipment.
3.  **Output:** Produces clean, commented `.mml` files ready for batch execution via U2000/NCE-T.

## 📋 Prerequisites

* Python 3.8+
* pandas
* openpyxl

## 📦 Installation

```bash
git clone [https://github.com/YourUsername/LinkMind-Sovereign.git](https://github.com/YourUsername/LinkMind-Sovereign.git)
cd LinkMind-Sovereign
pip install -r requirements.txt