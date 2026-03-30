# ghost-partisan-desktop
# 🛡️ GHOST-PARTISAN
**Sovereign. Decentralized. Anonymous.**

GHOST-PARTISAN is a portable Windows communication suite designed for journalists, activists, and privacy enthusiasts who require high-level anonymity without the footprint of mainstream apps.

[🌐 Visit Official Landing Page](https://partisan-dev.page.gd) | [🛒 Get License Key](https://payhip.com/b/YOUR_ID)

---

## 🚀 Key Features

* **Onion-Signaling:** Handshakes are routed through the Tor network to hide your IP from the start.
* **True P2P Video/Chat:** Direct encrypted streams between peers via WebRTC. No central servers.
* **Zero Identifiers:** No phone numbers, no emails, no Google/Apple accounts. Just your Ghost ID.
* **☢️ Panic Wipe (Alt+X):** Instant cryptographic shredding of your local vault and salt files.
* **Portable Design:** Runs as a standalone `.exe`. Zero installation required.

---

## 🛠️ Technical Architecture

### Encryption Engine
* **Vault:** AES-256 (Fernet) encryption.
* **KDF:** PBKDF2HMAC with SHA256 and unique local salting.
* **Transport:** DTLS/SRTP for secure P2P media streams.

### Signaling Protocol
GHOST-PARTISAN utilizes a "Blind Relay" system. Our PHP signaling gates act as a post-office: they pass encrypted handshake data (SDP/ICE) between peers but cannot read the contents or log the sender's true IP thanks to the integrated Tor proxy.

---

## 📁 Repository Structure
This repository serves as the public documentation and issue tracker for the project.

* `/docs`: Detailed encryption whitepaper and user guides.
* `/relays`: (Coming Soon) Open-source PHP scripts for hosting your own private signaling gates.
* `ISSUES.md`: Known bugs and planned feature roadmap.

---

## ⚖️ Safety & Disclaimer
GHOST-PARTISAN is provided "as-is." While it utilizes industry-standard encryption, no tool can guarantee 100% protection against all threat models. 

**The "Panic Wipe" is permanent.** Triggering a wipe deletes all contact data and keys. There is no recovery.

---

## 💬 Community & Support
* **Found a bug?** Please open an [Issue](https://github.com/ghost-partisan/ghost-partisan-desktop/issues).
* **Want to contribute?** We are currently looking for testers for the upcoming Android/Kotlin build.
* **B2B/Enterprise:** For private relay infrastructure or white-labeling, contact us via the site.

---
*Copyright © 2026 GHOST-PARTISAN. All Rights Reserved.*
