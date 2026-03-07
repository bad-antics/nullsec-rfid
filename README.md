<div align="center">

# 🏷️ NullSec RFID

### RFID & NFC Security Analysis Toolkit

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)]()
[![C](https://img.shields.io/badge/C-libnfc-A8B9CC?style=for-the-badge&logo=c&logoColor=black)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)]()
[![NullSec](https://img.shields.io/badge/NullSec-Linux_v5.0-00ff41?style=for-the-badge&logo=linux&logoColor=white)](https://github.com/bad-antics/nullsec-linux)

*RFID/NFC card analysis, cloning, emulation, and access control security testing*

</div>

---

## 🎯 Overview

NullSec RFID provides comprehensive tools for testing RFID and NFC-based access control systems. From low-frequency proximity cards to high-frequency smart cards, it covers the full spectrum of contactless security research.

## ⚡ Features

| Feature | Description |
|---------|-------------|
| **Card Reader** | Read and dump data from 125 kHz and 13.56 MHz cards |
| **Card Cloner** | Clone EM4100, HID ProxII, Indala, and Mifare cards |
| **Key Cracker** | Mifare Classic nested/darkside/hardnested attacks |
| **NFC Emulator** | Emulate cards for replay and relay testing |
| **NDEF Parser** | Parse and craft NFC Data Exchange Format messages |
| **Access Auditor** | Test physical access control configurations |

## 🔧 Supported Cards

| Card Type | Frequency | Read | Clone | Crack |
|-----------|-----------|:----:|:-----:|:-----:|
| EM4100 | 125 kHz | ✅ | ✅ | N/A |
| HID ProxII | 125 kHz | ✅ | ✅ | N/A |
| Indala | 125 kHz | ✅ | ✅ | N/A |
| Mifare Classic 1K/4K | 13.56 MHz | ✅ | ✅ | ✅ |
| Mifare Ultralight | 13.56 MHz | ✅ | ✅ | N/A |
| Mifare DESFire | 13.56 MHz | ✅ | ⚠️ | ⚠️ |
| NTAG 213/215/216 | 13.56 MHz | ✅ | ✅ | N/A |
| iCLASS | 13.56 MHz | ✅ | ⚠️ | ⚠️ |

## 🚀 Quick Start

```bash
# Scan for nearby cards
nullsec-rfid scan

# Read a Mifare Classic card
nullsec-rfid read --type mifare -o card_dump.json

# Run key recovery attack
nullsec-rfid crack --method hardnested --known-key FFFFFFFFFFFF

# Clone card to blank
nullsec-rfid clone --source card_dump.json --target T55x7

# Parse NFC NDEF data
nullsec-rfid ndef --parse tag_data.bin
```

## 🔗 Related Projects

| Project | Description |
|---------|-------------|
| [nullsec-sdr](https://github.com/bad-antics/nullsec-sdr) | Software-defined radio toolkit |
| [nullsec-glitch](https://github.com/bad-antics/nullsec-glitch) | Voltage glitching attacks |
| [nullsec-flipper-suite](https://github.com/bad-antics/nullsec-flipper-suite) | Flipper Zero payloads (430+ files) |
| [nullsec-linux](https://github.com/bad-antics/nullsec-linux) | Security Linux distro (140+ tools) |

## ⚠️ Legal

For **authorized security testing only**. Cloning access cards without authorization is illegal.

## 📜 License

MIT License — [@bad-antics](https://github.com/bad-antics)

---

<div align="center">

*Part of the [NullSec Hardware Security Suite](https://github.com/bad-antics)*

</div>
