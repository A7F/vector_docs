[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGenerateEphemeralKeyPair.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalGenerateEphemeralKeyPair

# SecurityLocalGenerateEphemeralKeyPair

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SecurityLocalGenerateEphemeralKeyPair(dword curve, byte publicKey[], dword* publicKeyLength, byte privateKey[], dword* privateKeyLength);
```

## Description

Generates a key pair to use in shared secret generation using the Elliptic Curve Diffie-Hellman (ECDH) protocol. Currently the curves NIST P-256, NIST P-384 and NIST P-521 are supported.

## Parameters

- **dword curve**  
  The elliptic curve to use for key pair generation.  
  Possible Values:
  - 10 → NIST P-256
  - 11 → NIST P-384
  - 12 → NIST P-521

- **byte publicKey[]** [OUT]  
  The generated public key in the uncompressed form 0x04 | HEX(x) | HEX(y).

- **dword publicKeyLength** [IN/OUT]  
  The length of the generated public key
  - NIST P-256: 65 bytes (uncompressed)
  - NIST P-384: 97 bytes (uncompressed)
  - NIST P-521: 133 bytes (uncompressed)

- **byte privateKey[]** [OUT]  
  The generated private key.

- **dword privateKeyLength** [IN/OUT]  
  The length of the generated private key.
  - NIST P-256: 32 bytes
  - NIST P-384: 48 bytes
  - NIST P-521: 66 bytes

## Return Values

- **1**  
  Success  
  A Value of 1 means that the action was successful.

- **<= 0**  
  Error  
  A value less than or equal to 0 means error.

## Example

```plaintext
dword curve = 10;

byte publicKey[65];
dword publicKeyLength = 65;
byte privateKey[32];
dword privateKeyLength = 32;

long result;

result = SecurityLocalGenerateEphemeralKeyPair(curve, publicKey, publicKeyLength, privateKey, privateKeyLength);
```

[SecurityLocalGenerateSharedSecret](CAPLfunctionSecurityLocalGenerateSharedSecret.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
