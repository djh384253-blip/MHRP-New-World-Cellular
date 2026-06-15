# 01_MHRP_System_Specification

## Overview
MHRP functions as an open-source, community-owned communication infrastructure designed to bypass centralized telecommunication giants and mass-surveillance architectures. It leverages Software Defined Radio (SDR) technology and decentralized mesh networking.

## Technical Architecture
* **Micro-Footprint OS:** Hardened Buildroot Linux running entirely in volatile RAM (initramfs) to mitigate physical tampering and provide a secure execution environment.
* **Custom ECB Board:** Integrates the AX5043 transceiver chip for Sub-GHz full-duplex cellular operation with minimal power consumption.
* **Zero-Trust Identity:** Bypasses legacy SIM numbers by using a cryptographic hash of your `Curve25519` public key for absolute privacy and anonymity.

## Connection Hierarchy
* **Tier 1:** Direct Peer-to-Peer (Native SDR-to-SDR) – Within close range communication without infrastructure.
* **Tier 2:** Mobile / Keychain Node (~100-Foot Personal Bubble) – On-person or vehicle-based mobile coverage.
* **Tier 3:** Fixed Home Node (~1,000-Foot Base Bubble) – Sub-GHz ISM Band cellular broadcast for regional coverage.
* **Tier 4:** Decentralized Mesh Fallback – Ambient Wave / Multi-Hop Grid for ultimate network resilience.

## Mission Goals
* **Regenerative Production Fund:** 100% of community donations fund subsidized hardware kits for strategic, high-surveillance geographic gaps where privacy is most needed.
* **Privacy Commitment:** All code is audited and telemetry-free. We maintain absolute transparency about what our system does.