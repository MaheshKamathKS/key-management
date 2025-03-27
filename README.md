# key-management
# Secure Key Management System

## Overview
The Secure Key Management System (KMS) ensures robust cryptographic key handling, supporting both symmetric and asymmetric encryption. It provides essential functionalities such as:
- **Key Generation**: AES and RSA key generation.
- **Key Storage and Revocation**: Secure storage with a Key Revocation List (KRL) for tracking compromised keys.
- **Authentication and Signing**: RSA-based message signing and verification.
- **Diffie-Hellman Key Exchange**: Secure key exchange between communicating parties.
- **Public Key Infrastructure (PKI)**: Management of trusted keys and X.509 certificates.

## Features
✅ **AES & RSA Key Generation**: Secure generation of symmetric and asymmetric keys.  
✅ **Key Revocation Management**: Maintain a Key Revocation List (KRL) to track compromised keys.  
✅ **Authentication & Signing**: Sign and verify messages using RSA keys.  
✅ **Diffie-Hellman Key Exchange**: Securely exchange keys with peers.  
✅ **Public Key Infrastructure (PKI)**: Manage trusted X.509 certificates.  
✅ **Secure Key Storage**: Controlled access and secure storage of keys.  

---

## Project Structure
```
Secure-KMS/
│── key_ex.py              # Handles Diffie-Hellman key exchange
│── aes_keygen.py          # Generates AES keys
│── rsagen.py              # Generates RSA key pairs
│── certificate_manager.py # Manages X.509 certificates
│── krl_manager.py         # Handles key revocation
│── authentication.py      # Manages authentication & signing
│── main.py                # Main interface for system operations
│── krl.json               # Stores revoked key identifiers
│── README.md              # Project documentation
```

---

## Installation & Setup

### Prerequisites
Ensure you have the following installed:
- Python 3.8+
- `cryptography` library

### Install Dependencies
Run the following command:
```bash
pip install cryptography
```

### Run the Main Application
To start the KMS, execute:
```bash
python main.py
```

---

## Usage Guide

### 1. Generate AES and RSA Keys
Run the following commands to generate keys:
```bash
python aes_keygen.py
python rsagen.py
```
- This generates `aes_key.bin`, `private_key.pem`, and `public_key.pem`.
- Revoked keys are automatically removed.

### 2. Revoke a Key
To revoke a key, run:
```bash
python krl_manager.py
```
Enter the filename (e.g., `private_key.pem`) to revoke it.

### 3. Check Key Revocation Status
Use the `check_key_status()` function in `krl_manager.py` to determine if a key is revoked.

### 4. Sign and Verify Data
To sign and verify messages using RSA keys, run:
```bash
python authentication.py
```

### 5. Perform Diffie-Hellman Key Exchange
To generate a Diffie-Hellman key pair, run:
```bash
python key_ex.py
```
To compute a shared secret with a peer's public key:
```bash
python key_ex.py compute_shared_secret peer_public_key.pem
```

---

## Security Considerations
- 🔒 **Protect Private Keys**: Store `private_key.pem` securely and restrict access.
- 🔑 **Use Strong Key Sizes**: Default RSA key size is 2048 bits for enhanced security.
- 🔄 **Regular Key Rotation**: Periodically generate new keys to maintain security.
- ⚠️ **Monitor Revoked Keys**: Ensure revoked keys are not used accidentally.

---

## License
This project is licensed under the MIT License. See `LICENSE` for details.

---

## References
Based on principles from: [Key Management System](https://github.com/neilplus21/key_mgmt_system/blob/main/README.md)

