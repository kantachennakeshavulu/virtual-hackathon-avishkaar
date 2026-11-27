# 🛠️ Integrated Forensic Tool Suite — Architecture & Technical Reference

This document details the 14 browser-native and external forensic integrations embedded within the **Zero-Trust Digital Forensics & Incident Response (DFIR) Platform**.

All forensic actions executed through these modules are bound to the active Case Reference ID, cryptographically signed, and committed to the immutable Chain of Custody ledger.

---

## 📋 Comprehensive Tool Matrix

| S. No. | Tool Name | Category | Primary Forensic Capability | Standards Compliance |
| :---: | :--- | :--- | :--- | :--- |
| **01** | **🖥️ FTK Imager** | Disk Forensics | Bitstream raw disk imaging & SHA-256/MD5 hash validation | ISO/IEC 27037 |
| **02** | **🗂️ Autopsy / TSK** | File System Carving | Deleted file recovery, MAC timeline analysis & bodyfile parsing | NIST SP 800-86 |
| **03** | **📷 ExifTool** | Media Forensics | Camera metadata extraction, timestamp verification & live GPS mapping | RFC 7946 (GeoJSON) |
| **04** | **🛡️ Microsoft Defender** | Threat Scanning | Static file signature analysis & heuristic behavioral detection | MITRE ATT&CK |
| **05** | **📦 Sandbox Environment** | Malware Detonation | Isolated execution monitoring & dynamic threat scoring | Heuristic EDR |
| **06** | **🌐 VirusTotal API** | Threat Intel | Real-time cloud hash reputation & multi-engine malware triage | RFC 9110 (REST) |
| **07** | **🧠 Volatility 3** | Memory Forensics | Volatile RAM inspection, hidden process detection & rootkit analysis | NIST SP 800-101 |
| **08** | **📱 Cellebrite UFED** | Mobile Forensics | Logical smartphone extraction, call logs, SMS, and contacts parsing | SWGDE Standards |
| **09** | **🦈 Wireshark** | Network Forensics | Scapy-powered PCAP packet dissection & traffic anomaly identification | RFC 791 / RFC 793 |
| **10** | **📊 Web Log Analyzer** | SIEM / Telemetry | Reverse-proxy access log parsing (`X-Forwarded-For`) & brute-force audit | CIS Controls v8 |
| **11** | **🕵️ The Sleuth Kit CLI** | Low-Level FS | Command-line raw inode and master file table (MFT) examination | POSIX / NTFS Spec |
| **12** | **🌍 OSINT Tracker** | Threat Intelligence | Live IP geolocation, ASN lookup & open-source domain telemetry | RFC 1035 |
| **13** | **🖼️ Steganography** | Anti-Forensics | Least Significant Bit (LSB) hidden payload extraction in images | Digital Watermarking |
| **14** | **🔑 Hashcat** | Cryptanalysis | Offline cryptographic hash verification & password entropy audit | FIPS PUB 180-4 |

---

## 🔍 Module Details & Forensic Workflows

### 1. Disk & File System Forensics (FTK Imager & Autopsy)
- **Ingestion:** Reads raw bitstream images (`.dd`, `.raw`, `.img`, `.E01`) in 64 KB binary chunks.
- **Verification:** Automatically calculates pre- and post-acquisition SHA-256 and MD5 hashes to guarantee zero media contamination during ingestion.
- **Carving:** Parses unallocated disk clusters to recover deleted evidence files and builds historical timeline charts based on Modified, Accessed, and Created (MAC) timestamps.

### 2. Network Traffic & Telemetry Forensics (Wireshark & Scapy)
- **Ingestion:** Parses live `.pcap` and `.pcapng` network packet captures.
- **Protocol Analysis:** Dissects Ethernet, IPv4, IPv6, TCP, UDP, DNS, and HTTP payloads.
- **Anomaly Detection:** Flags suspicious connection bursts, port scanning signatures, and unencrypted cleartext data transmission.

### 3. Memory Forensics (Volatility 3)
- **Volatile Ingestion:** Analyzes raw system memory captures (`.raw`, `.vmem`, `.dmp`).
- **Core Plugins:**
  - `windows.pslist.PsList`: Enumerates active and unlinked process structures.
  - `windows.netscan.NetScan`: Identifies active socket connections and listening ports at the moment of acquisition.
  - `windows.malfind.Malfind`: Detects injected code and suspicious memory pages marked as executable.

### 4. Mobile Device Forensics (Cellebrite UFED)
- **Schema Parsing:** Decodes physical and logical extraction dumps formatted in structured XML.
- **Artifacts Mapped:** Organizes suspect contacts, outgoing/incoming/missed call records, and deleted SMS threads into an interactive forensic table.

### 5. Media & Anti-Forensics Analysis (ExifTool & Stego)
- **EXIF Extraction:** Extracts EXIF/TIFF headers, camera hardware serial numbers, exposure metadata, and GPS latitude/longitude coordinates.
- **Social Media Stripping Detection:** Flags when an image has had its metadata stripped by platforms like WhatsApp or Facebook.
- **LSB Steganography:** Analyzes red, green, and blue (RGB) color channels to recover hidden binary payloads concealed inside image pixels.

---

## 🔒 Chain of Custody & Non-Repudiation

Whenever an investigator launches any of the above 14 tools:
1. **Actor ID:** The examiner's authenticated user ID and role are extracted from the zero-trust session.
2. **Network Origin:** The physical device IP address is captured via reverse-proxy header inspection.
3. **Timestamp:** High-resolution ISO 8601 Indian Standard Time (IST) is recorded.
4. **Action Commitment:** The operation description and generated artifacts are committed to the immutable case ledger and automatically compiled into the final **Section 65B Court Case Dossier**.
