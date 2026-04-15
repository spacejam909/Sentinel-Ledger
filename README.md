# Sentinel-Ledger
# Sentinel Ledger: Secure Financial Auditor

**Sentinel Ledger** is a security-focused financial management tool designed to bridge the gap between personal budgeting and forensic data integrity. Unlike standard trackers, this application implements cryptographic hashing to ensure that financial records remain tamper-proof and uses anomaly detection to flag potential fraudulent activity.

---

## 🛡️ Core Security Features

* **Cryptographic Integrity Checks:** Every transaction is stored with a unique **SHA-256 HMAC** (Hash-based Message Authentication Code). If a database record is modified externally, the application detects the signature mismatch and flags the entry as compromised.
* **Biometric Access Control:** Leveraging **iOS LocalAuthentication**, the app integrates FaceID/TouchID, ensuring sensitive financial data is only accessible to the authenticated owner.
* **Anomaly Detection Engine:** A custom logic layer that monitors "Transaction Velocity." It automatically flags patterns consistent with card-testing attacks (e.g., multiple low-value transactions in rapid succession).
* **Secure Credential Storage:** Utilizes the **iOS Keychain (Secure Enclave)** for storing encryption keys and sensitive tokens, preventing data leaks in the event of a device compromise.

## 🛠️ Technical Stack

* **Frontend:** SwiftUI (iOS) with a focus on high-fidelity haptics and a gamified UI.
* **Backend:** Java (for forensic auditing logic and data parsing).
* **Database:** SQLite with **SQLCipher** for full-disk encryption at rest.
* **Security:** SHA-256 Hashing, AES-256 Encryption, and OWASP-aligned defensive programming.

## 🚀 Getting Started

### Prerequisites
* **Xcode 15+**
* **JDK 17+**
* **CocoaPods** (for dependency management)

### Installation
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/sentinel-ledger.git](https://github.com/yourusername/sentinel-ledger.git)
    ```
2.  **Install dependencies:**
    ```bash
    cd sentinel-ledger && pod install
    ```
3.  **Launch:**
    Open `SentinelLedger.xcworkspace` in Xcode and build for your target device or simulator.

## 📈 Project Roadmap

- [x] Implement core CSV parsing and SQL storage logic.
- [x] Integrate HMAC-based data validation for all transaction rows.
- [ ] Add real-time bank API integration via Plaid.
- [ ] Expand gamification engine (Reward tiers for "Audit Streaks").

## 🧠 Why This Project Exists
This project was developed as a deep dive into **Security-by-Design**. The goal was to move away from "trusting" the database and instead build a system that assumes an adversarial environment. By requiring constant verification of data integrity and implementing biometric gates, this tool treats personal budget data with the same gravity as enterprise financial records.

---
*Developed as a portfolio project for Software Engineering and Cybersecurity Internship applications.*
