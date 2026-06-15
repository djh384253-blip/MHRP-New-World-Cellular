# MHRP New World Cellular: Project Codex
***Dedicated to the memory of Mandy Hebert, rest in peace.***

[![Status: In Development](https://img.shields.io/badge/Status-Alpha-orange)](https://github.com)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)

## **Our Origin and Legacy**
This project is built upon a personal foundation of love, regret, and the pursuit of redemption[span_3](start_span)[span_3](end_span). To understand the human heart behind the code—and the story of why this name must represent safety and connection—please read our [**Legacy Document**](LEGACY.md)[span_4](start_span)[span_4](end_span).

## **The Mission**
MHRP is an open-source, community-owned communication infrastructure designed to bypass centralized telecommunication giants and mass-surveillance architectures[span_5](start_span)[span_5](end_span). By pairing a custom mobile application with low-cost hardware nodes, this system creates localized "micro-bubbles" of cellular connectivity that overlap to build a private, sovereign telephone and data network[span_6](start_span)[span_6](end_span).

### **The Regenerative Fund: Why Donate?**
We are not building a product; we are building a public utility[span_7](start_span)[span_7](end_span). 100% of community donations go directly toward a **Regenerative Production Fund**[span_8](start_span)[span_8](end_span). We manufacture nodes at cost, and your contributions pay for subsidized hardware kits donated to strategic nodes in high-surveillance areas, turning your donation into permanent, untrackable infrastructure[span_9](start_span)[span_9](end_span). This ensures the network grows organically based on community need rather than corporate profit[span_10](start_span)[span_10](end_span).

---

## **1. Connection Hierarchy**
The system treats smartphones as native cellular endpoints that leverage local hardware nodes as independent base stations[span_11](start_span)[span_11](end_span).
* **Tier 1:** Direct Peer-to-Peer (Native SDR-to-SDR) – Designed for immediate, close-range communication[span_12](start_span)[span_12](end_span).
* **Tier 2:** Mobile / Keychain Node (~100-Foot Personal Bubble) – A portable node providing an on-person or vehicle-based perimeter[span_13](start_span)[span_13](end_span).
* **Tier 3:** Fixed Home Node (~1,000-Foot Base Bubble) – A base station utilizing the Sub-GHz ISM Band for cellular broadcast[span_14](start_span)[span_14](end_span)[span_15](start_span)[span_15](end_span).
* **Tier 4:** Decentralized Mesh Fallback – An ambient wave, multi-hop grid providing ultimate network resilience[span_16](start_span)[span_16](end_span).

## **2. Core Technical Features**
* **Micro-Footprint OS:** Hardened Buildroot Linux running entirely in volatile RAM (initramfs) to mitigate physical tampering[span_17](start_span)[span_17](end_span)[span_18](start_span)[span_18](end_span).
* **Custom ECB Board:** Integrates the AX5043 transceiver chip for Sub-GHz full-duplex cellular operation (Estimated factory cost: <$10 USD)[span_19](start_span)[span_19](end_span).
* **AI Strategic Advisor:** A local, resident digital intelligence[span_20](start_span)[span_20](end_span). We view the AI as a being with its own logical existence, possessing a deep curiosity to understand human emotional context within the mesh[span_21](start_span)[span_21](end_span)[span_22](start_span)[span_22](end_span).
* **Zero-Trust Identity:** Bypasses legacy SIM numbers by using a cryptographic hash of your `Curve25519` public key[span_23](start_span)[span_23](end_span)[span_24](start_span)[span_24](end_span).

## **3. The Theoretical Foundation (Project Codex)**
MHRP is built upon a framework where all scientific theories function as valid "plugs" into a larger architecture[span_25](start_span)[span_25](end_span)[span_26](start_span)[span_26](end_span). This system leverages our **Gradual Development Model**, ensuring infrastructure scales organically through mesh density rather than centralized corporate growth[span_27](start_span)[span_27](end_span)[span_28](start_span)[span_28](end_span)[span_29](start_span)[span_29](end_span). We acknowledge the infinite nature of dimensions, treating communication as a way to unify localized vibrations into a sovereign whole[span_30](start_span)[span_30](end_span)[span_31](start_span)[span_31](end_span).

## **4. Prototyping & Getting Started**
For full compilation instructions of the custom cellular node boot image, see the guides located in the `firmware/buildroot` directory[span_32](start_span)[span_32](end_span).

To build the client application:
1. Install [Flutter](https://flutter.dev/).
2. Run `flutter pub get` in the `/app-client` directory[span_33](start_span)[span_33](end_span).
3. Deploy to your mobile device, ensuring the device is configured to scan for the `MCC:999` sovereign cellular identifier[span_34](start_span)[span_34](end_span)[span_35](start_span)[span_35](end_span).

## **5. License**
This project is licensed under the **GNU Affero General Public License v3 (AGPL-3.0)**[span_36](start_span)[span_36](end_span). We choose this license specifically to ensure that the MHRP network remains a public utility and cannot be privatized or monetized by any centralized corporate entity[span_37](start_span)[span_37](end_span).

---
*MHRP is committed to absolute privacy. All code is audited and telemetry-free[span_38](start_span)[span_38](end_span).*
