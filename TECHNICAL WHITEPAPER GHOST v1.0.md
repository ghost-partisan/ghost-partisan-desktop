# **📑 TECHNICAL WHITEPAPER: GHOST-PARTISAN v1.0**



## **Subject: Zero-Knowledge P2P Communication \& Onion-Routed Signaling Architecture**



**1. Executive Summary**



GHOST-PARTISAN is a decentralized communication suite designed to eliminate central points of failure and metadata collection. It achieves this by decoupling Signaling (connection setup) from Transport (data stream) and wrapping the initial handshake in the Tor network.



**2. Cryptographic Foundation**



The application utilizes industry-standard primitives to ensure Confidentiality, Integrity, and Authenticity (CIA).



**Local Data-at-Rest:** User vaults are encrypted using AES-256-CBC via the Fernet specification.



**Key Derivation:** Master passwords are run through PBKDF2HMAC (SHA256) with a minimum of 100,000 iterations and a unique 16-byte local salt.



**Session Security:** Peer-to-peer streams utilize DTLS (Datagram Transport Layer Security) and SRTP (Secure Real-time Transport Protocol) for end-to-end encrypted voice and video.



**3. The "Onion-Signaling" Protocol**



Standard WebRTC applications often leak the user's IP address to a central STUN/TURN or Signaling server during the "handshake" phase. GHOST-PARTISAN mitigates this through Onion-Signaling:



**Handshake Generation:** The app generates an encrypted Session Description Protocol (SDP) offer.



**Tor Proxying:** The app initiates a local SOCKS5 proxy to the Tor network.



**Blind Relay:** The encrypted handshake is sent through the Tor circuit to a "Blind" PHP Relay.



**Metadata Stripping:** The Relay server only sees the exit node's IP address, never the user’s true IP. The relay acts as a temporary "dead drop" for the peer to collect the handshake.



**4. Anti-Forensic Measures**



GHOST-PARTISAN is designed with a "Volatile-First" philosophy.



**No Registry Footprint:** The application is portable and does not write to the Windows Registry.



**The Panic Trigger:** Upon activation of the Alt+X sequence, the application executes a cryptographic wipe of the vault.salt and ghost.db files. Because the master key is derived from these files, the data becomes mathematically unrecoverable (ciphertext entropy).



**5. Threat Model \& Limitations**



**In-Scope:** Protection against ISP surveillance, centralized data breaches, and localized physical seizure (via Panic Wipe).



**Out-of-Scope:** Advanced side-channel attacks (RAM dumping), hardware-level keyloggers, or OS-level compromises.



"For formal security audits or B2B infrastructure inquiries, contact: [partisan.dev@proton.me](partisan.dev@proton.me)."

