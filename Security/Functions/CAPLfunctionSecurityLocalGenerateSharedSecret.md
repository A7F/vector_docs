# SecurityLocalGenerateSharedSecret

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `SecurityLocalGenerateSharedSecretECDH` and respectively `LocalSecurityGenerateSharedSecretECDH`.

## Function Syntax

```plaintext
`long SecurityLocalGenerateSharedSecret(dword curve, byte publicKey[], dword publicKeyLength, byte privateKey[], dword privateKeyLength, byte sharedSecret[], dword* sharedSecretLength);`
```

## Description

Generates a shared secret between A and B using the Elliptic Curve Diffie-Hellman (ECDH) protocol. Currently the curves NIST P-256, NIST P-384, NIST P-521 and X25519 are supported.

## Parameters

- **dword curve**  
  The elliptic curve to use for shared secret generation.  
  Possible Values:
  - 10 → NIST P-256
  - 11 → NIST P-384
  - 12 → NIST P-521
  - 20 → X25519

- **byte publicKey[]**  
  The public key of A. Supported are the uncompressed form `0x04 | HEX(x) | HEX(y)` as well as the compressed forms `0x02 | HEX(x)` (for even y) OR `0x03 | HEX(x)` (for odd y).

- **dword publicKeyLength**  
  The length of the generated public key.
  - NIST P-256: 65 bytes (uncompressed) or 32 bytes (compressed)
  - NIST P-384: 97 bytes (uncompressed) or 49 bytes (compressed)
  - NIST P-521: 133 bytes (uncompressed) or 67 bytes (compressed)
  - X25519: 32 bytes

- **byte privateKey[]**  
  The private key of B.

- **dword privateKeyLength**  
  The length of the private key of B.
  - NIST P-256: 32 bytes
  - NIST P-384: 48 bytes
  - NIST P-521: 66 bytes
  - X25519: 32 bytes

- **byte sharedSecret[]** [OUT]  
  The generated shared secret.

- **dword sharedSecretLength** [IN/OUT]  
  The length of the generated shared secret.
  - NIST P-256: 32 bytes
  - NIST P-384: 48 bytes
  - NIST P-521: 66 bytes
  - X25519: 32 bytes

## Return Values

- **1**  
  Success  
  A value of 1 means that the action was successful.

- **\<= 0**  
  Error  
  A value less than or equal to 0 means error.

## Example

```plaintext
dword curve = 10;
byte publicKey[65] = {0x04, 0xDA, 0xD0, 0xB6, 0x53, 0x94, 0x22, 0x1C, 0xF9, 0xB0, 0x51, 0xE1, 0xFE, 0xCA, 0x57, 0x87, 0xD0, 0x98, 0xDF, 0xE6, 0x37, 0xFC, 0x90, 0xB9, 0xEF, 0x94, 0x5D, 0x0C, 0x37, 0x72, 0x58, 0x11, 0x80, 0x52, 0x71, 0xA0, 0x46, 0x1C, 0xDB, 0x82, 0x52, 0xD6, 0x1F, 0x1C, 0x45, 0x6F, 0xA3, 0xE5, 0x9A, 0xB1, 0xF4, 0x5B, 0x33, 0xAC, 0xCF, 0x5F, 0x58, 0x38, 0x9E, 0x05, 0x77, 0xB8, 0x99, 0x0B, 0xB3};
dword publicKeyLength = 65;
byte privateKey[32] = {0xC6, 0xEF, 0x9C, 0x5D, 0x78, 0xAE, 0x01, 0x2A, 0x01, 0x11, 0x64, 0xAC, 0xB3, 0x97, 0xCE, 0x20, 0x88, 0x68, 0x5D, 0x8F, 0x06, 0xBF, 0x9B, 0xE0, 0xB2, 0x83, 0xAB, 0x46, 0x47, 0x6B, 0xEE, 0x53};
dword privateKeyLength = 32;
byte sharedSecret[32];
dword sharedSecretLength = 32;

long result;

result = SecurityLocalGenerateSharedSecret(curve, publicKey, publicKeyLength, privateKey, privateKeyLength, sharedSecret, sharedSecretLength);
```

[SecurityLocalGenerateEphemeralKeyPair](CAPLfunctionSecurityLocalGenerateEphemeralKeyPair.md)
