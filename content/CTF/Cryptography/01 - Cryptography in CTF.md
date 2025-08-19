---
title: Cryptography in CTF
tags:
  - Crypto
  - ctf
draft: true
---

# Simple Cipher

- Shift Ciphers
- Substitution Ciphers
- Transposition
- Frequency Analysis

## Tools
- quipquip
- dcode.fr

# Modern Crypto Primitives

### Hashes

- MD5
- SHA1
- SHA256

### Block Ciphers
- AES
- DES

### Modes of Operations

- ECB
- CBC
- CTR
- GCM

### Asymmetric Crypto

- RSA
- ECC

## Tools List

- openssl
- hashcat
- RsaCtfTool

# Common CTF Crypto Vulnerabilities

### RSA Attacks

- Common Modulus
- Low Exponent Attack
- Wiener's Attack
- Fermat's Factorization

### AES/Block Ciphers

- ECB Pattern Leakage
- CBC bit - flipping attack

### Padding Oracle Attacks

- Exploit incorrect padding checks

### Diffie-Hellman Weaknesses

- Small Primes
- Reused Parameters

### Elliptic Curve 

- ECDSA Nonce reuse attacks
- Baby step giant step {pollard rho}


# How to Approach

- Always check if **parameters are weak** (short key, reused nonce, low exponent).
- Try **known plaintext attacks** (ECB, CTR leaks).
- Look for **padding errors** (CBC, PKCS#7).
- Automate with **Python scripts** (pwntools + pycryptodome).

# Tools List

***Hash Cracking:***
- John the Reaper
- Hashcat
- Hydra
- Online Hash Cracker


***Encryption Decryption:***
- CyberChef
*URL:* https://gchq.github.io/CyberChef/

- OpenSSL 

- `base64` command

- SageMath {Python}

- RsaCtfTool
*URL*: https://github.com/Ganapati/RsaCtfTool

- Cipher Identifier
*URL*: https://www.dcode.fr/cipher-identifier

