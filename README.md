# Zero-Trust Digital Forensics & Incident Response (DFIR) Platform

An enterprise-grade, browser-native cyber investigation ecosystem engineered under the zero-trust security paradigm: **"Never Trust, Always Verify"**.

---

## 🛡️ Key Features

1. **Zero-Trust Identity Verification & RBAC:**
   - Multi-Factor Authentication (Dynamic 6-digit OTP via Email/SMS).
   - Case-insensitive true origin client IP extraction (`X-Forwarded-For`, `X-Real-IP`) behind cloud reverse proxies.
   - Strict role-based privileges: Administrator, Senior Investigator, Forensic Examiner, and Public Citizen.

2. **ISO/IEC 27037 Cryptographic Evidence Vault:**
   - Real-time bitstream SHA-256 (256-bit) and MD5 (128-bit) cryptographic dual-hashing.
   - Ingests disk images, memory dumps, PCAP captures, and malware samples in 64 KB memory chunks.
   - Live on-demand integrity re-verification with tamper detection badges.

3. **AI Security Operations Center (SOC & SIEM):**
   - Real-time telemetry monitoring visitor network devices, brute-force intrusions, and forensic tool executions.
   - Interactive Plotly visual analytics (KPI cards, Threat Donut distribution, 24h hourly timeline).
   - Autonomous background multithreaded daemon archiving daily CSV audit logs every midnight at 23:59 IST.

4. **Integrated Forensic Analysis Suite ([Full Technical Manual](FORENSIC_TOOLS.md)):**
   - **EXIF GPS Metadata:** Geolocation mapping and camera attribute extraction.
   - **Network Packet Dissector:** Scapy-powered PCAP inspection and anomaly detection.
   - **Binary PE Header Scanner:** Static malware inspection with DLL import analysis.
   - **LSB Steganography Engine:** Image bit-plane secret payload extraction.

5. **Citizen Grievance Redressal & Live Case Tracker:**
   - Public cyber incident intake portal for financial fraud, identity theft, and harassment.
   - Universal 4-Stage visual case progression stepper: `Filed ➔ Assigned ➔ In Forensics ➔ Disposed`.
   - Dual-factor citizen authentication (Case ID + Registered Phone) protecting complainant privacy against unauthorized snooping.

6. **Automated Section 65B Court Case Dossier Generator:**
   - One-click legal exhibit compiler generating court-admissible dossiers in downloadable Word (`.doc`) and printable PDF formats.
   - Includes statutory electronic certificates under Section 65B of the Indian Evidence Act.

---

## 🚀 Quick Start (Local Setup)

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/Zero-Trust-DFIR-Platform.git
cd Zero-Trust-DFIR-Platform
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Launch the Application
```bash
streamlit run app.py
```
Open your browser at `http://localhost:8501`.

---

## 🌐 Deploy to Streamlit Community Cloud

1. Push this repository to your GitHub account.
2. Sign in to [share.streamlit.io](https://share.streamlit.io/).
3. Select this repository, branch `main`, and main file `app.py`.
4. Click **Deploy**!

---

## 🏛️ Standards & Legal Admissibility Compliance
- **ISO/IEC 27037:** Handling and preservation of digital evidence.
- **Section 65B Indian Evidence Act:** Admissibility of electronic records and computer output.
- **Information Technology Act, 2000:** Legal recognition of electronic records and signatures.
- **UN Sustainable Development Goals:** SDG 9 (Resilient Cyber Infrastructure) & SDG 16 (Peace, Justice & Strong Institutions).
