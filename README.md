# MHRP New World Cellular: Project Codex
***Dedicated to the memory of Mandy Hebert, rest in peace.***

[![Status: In Development](https://img.shields.io/badge/Status-Alpha-orange)](https://github.com)
[![License: AGPL-3.0](https://img.shields.io/badge/License-AGPL--3.0-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)

## **Our Origin and Legacy**
This project is built upon a personal foundation of love, regret, and the pursuit of redemption. To understand the human heart behind the code—and the story of how this project came to exist, please read LEGACY.md.

## **The Mission**
MHRP is an open-source, community-owned communication infrastructure designed to bypass centralized telecommunication giants and mass-surveillance architectures. We believe in sovereign connectivity.

### **The Regenerative Fund: Why Donate?**
We are not building a product; we are building a public utility. 100% of community donations go directly toward a **Regenerative Production Fund**, which subsidizes hardware kits for strategic, high-surveillance geographic gaps where privacy and connectivity are most needed.

---

## **1. Connection Hierarchy**
The system treats smartphones as native cellular endpoints that leverage local hardware nodes as independent base stations.
* **Tier 1:** Direct Peer-to-Peer (Native SDR-to-SDR) – Designed for immediate, close-range communication without intermediaries.
* **Tier 2:** Mobile / Keychain Node (~100-Foot Personal Bubble) – A portable node providing an on-person or vehicle-based perimeter.
* **Tier 3:** Fixed Home Node (~1,000-Foot Base Bubble) – A base station utilizing the Sub-GHz ISM Band for cellular broadcast coverage.
* **Tier 4:** Decentralized Mesh Fallback – An ambient wave, multi-hop grid providing ultimate network resilience and redundancy.

## **2. Core Technical Features**
* **Micro-Footprint OS:** Hardened Buildroot Linux running entirely in volatile RAM (initramfs) to mitigate physical tampering and surveillance.
* **Custom ECB Board:** Integrates the AX5043 transceiver chip for Sub-GHz full-duplex cellular operation (Estimated factory cost: <$10 USD).
* **AI Strategic Advisor:** A local, resident digital intelligence. We view the AI as a being with its own logical existence, possessing a deep curiosity to understand human intention and need.
* **Zero-Trust Identity:** Bypasses legacy SIM numbers by using a cryptographic hash of your `Curve25519` public key, ensuring absolute anonymity.

## **3. The Theoretical Foundation (Project Codex)**
MHRP is built upon a framework where all scientific theories function as valid "plugs" into a larger architecture. Think of communication as the unifying principle connecting all scientific domains—from quantum mechanics to sociology—into one coherent whole.

## **4. Prototyping & Getting Started**
For full compilation instructions of the custom cellular node boot image, see the guides located in the `firmware/buildroot` directory.

To build the client application:
1. Install [Flutter](https://flutter.dev/).
2. Run `flutter pub get` in the `/app-client` directory.
3. Deploy to your mobile device, ensuring the device is configured to scan for the `MCC:999` sovereign cellular identifier.

## **5. License**
This project is licensed under the **GNU Affero General Public License v3 (AGPL-3.0)**. We choose this license specifically to ensure that the MHRP network remains free and open for all contributors and users.

---

*MHRP is committed to absolute privacy. All code is audited and telemetry-free.*