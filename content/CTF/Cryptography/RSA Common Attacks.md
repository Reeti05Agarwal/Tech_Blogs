---
title: Common Modulus
tags:
  - Crypto
  - rsa
---

# Common Modulus
Two Different RSA public exponents encrypt the same plaintext with the same modulus

***Given:***
1. a Shared Modulus `n`
2. Two Different public exponents `e1` and `e2`
3. Two ciphertexts `c1` and `c2` (encrypted with same plaintext m)

***Finding:***
1. Original Plaintext `m`

***Why it works:***
- RSA is secured only if each use has their own modulus
- If two people share the same `n`, but have different `e`, then with GCD tricks, we can combine `c1`, `c2`  to recover `m`.

***Script:***
https://github.com/HexPandaa/RSA-Common-Modulus-Attack

***Resources:***
https://github.com/ashutosh1206/Crypton/tree/master/RSA-encryption/Attack-Common-Modulus

***Challenge:***
https://github.com/ashutosh1206/Crypton/blob/master/RSA-encryption/Attack-Common-Modulus/Challenges/RSA-1s-Fun
# Low Exponent Attack



# Wiener's Attack


# Fermat's Factorization