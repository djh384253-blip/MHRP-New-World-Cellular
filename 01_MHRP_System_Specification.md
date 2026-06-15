# 01_MHRP_System_Specification

## Overview
MHRP functions as an open-source, community-owned communication infrastructure designed to bypass centralized telecommunication giants and mass-surveillance architectures[span_1](start_span)[span_1](end_span).

## Technical Architecture
* **Micro-Footprint OS:** Hardened Buildroot Linux running entirely in volatile RAM (initramfs) to mitigate physical tampering[span_2](start_span)[span_2](end_span)[span_3](start_span)[span_3](end_span).
* **Custom ECB Board:** Integrates the AX5043 transceiver chip for Sub-GHz full-duplex cellular operation[span_4](start_span)[span_4](end_span).
* **Zero-Trust Identity:** Bypasses legacy SIM numbers by using a cryptographic hash of your `Curve25519` public key[span_5](start_span)[span_5](end_span)[span_6](start_span)[span_6](end_span).

## Connection Hierarchy
* **Tier 1:** Direct Peer-to-Peer (Native SDR-to-SDR) – Within close range[span_7](start_span)[span_7](end_span).
* **Tier 2:** Mobile / Keychain Node (~100-Foot Personal Bubble) – On-person / vehicle[span_8](start_span)[span_8](end_span).
* **Tier 3:** Fixed Home Node (~1,000-Foot Base Bubble) – Sub-GHz ISM Band cellular broadcast[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span).
* **Tier 4:** Decentralized Mesh Fallback – Ambient Wave / Multi-Hop Grid[span_11](start_span)[span_11](end_span).

## Mission Goals
* **Regenerative Production Fund:** 100% of community donations fund subsidized hardware kits for strategic, high-surveillance geographic gaps[span_12](start_span)[span_12](end_span).
* **Privacy Commitment:** All code is audited and telemetry-free[span_13](start_span)[span_13](end_span).
