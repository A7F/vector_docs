[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalSignEcdsa.md)

## SecurityLocalSignEcdsa

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalSignEcdsa

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

`SecurityLocalSignEcdsa(dword curve, dword hashAlgorithm, dword signatureFormat, byte privateKey[], dword privateKeyLength, byte data[], dword dataLength, byte signature[], dword* signatureLength)`

### Description

Generates the signature of the data with a given private key using the ECDSA signature algorithm. The curve, hash algorithm and the signature format can be selected via the parameters.

### Parameters

- **dword curve**: ID of the curve to use.
  - Available curves:
    - brainpool256r1 = 1
    - brainpool384r1 = 2
    - brainpool512r1 = 3
    - secp256r1 = 4
    - secp384r1 = 5
    - secp521r1 = 6

- **dword hashAlgorithm**: ID of the hash algorithm to use.
  - Available hash algorithm:
    - SHA-256 = 1
    - SHA-384 = 2
    - SHA-512 = 3

- **dword signatureFormat**: ID of the signature format to use.
  - Available signature formats:
    - IEEE1363 = 0
    - DER sequence = 1

- **byte privateKey[]**: Private key to be used for signing.
  - The following formats are accepted:
    - raw key bytes
    - DER
    - PEM

- **dword privateKeyLength**: Length of private key to be used for signing.

- **byte data[]**: Data to be used for signing.

- **dword dataLength**: Length of data to be used for signing.

- **byte signature[] [OUT]**: Generated signature.

- **dword signatureLength [IN/OUT]**: Length of generated signature.

### Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.

- **≤ 0**: Error  
  A value less than or equal to 0 means error.

### Example

```plaintext
dword curve = 1; // brainpool256r1
dword hashAlgorithm = 1; // SHA-256
dword signatureFormat = 1; // DER sequence
byte privateKey[138] = 0x30,0x81,0x87,0x02,0x01,0x00,0x30,0x13,0x06,0x07,0x2a,0x86,0x48,0xce,0x3d,0x02,0x01,0x06,0x08,0x2a,0x86,0x48,0xce,0x3d,0x03,0x01,0x07,0x04,0x6d,0x30,0x6b,0x02,0x01,0x01,0x04,0x20,0x86,0xd6,0x1d,0x9e,0x43,0xfa,0x81,0xf9,0x46,0xad,0xac,0xf2,0x1b,0x14,0x60,0xb9,0xc8,0xb4,0xe6,0x5e,0x99,0x77,0xc7,0x13,0x9d,0x20,0x6c,0x46,0xb3,0x09,0xc8,0xb3,0xa1,0x44,0x03,0x42,0x00,0x04,0xd5,0xc1,0x3a,0xba,0xff,0x54,0x6b,0x36,0xd6,0x61,0x14,0x18,0x42,0x6e,0x55,0xb1,0x8d,0x34,0x71,0xfb,0x58,0xc5,0x36,0x04,0x11,0x91,0xed,0xa7,0x5b,0x45,0xd1,0xfb,0x1d,0xd6,0xa0,0x42,0xae,0x91,0x6b,0x70,0x6d,0x8f,0x9e,0x13,0x7b,0x6e,0xdf,0x5b,0x42,0x3c,0x13,0x02,0x06,0x13,0xb7,0x62,0x0a,0xf6,0x8b,0x7f,0xc8,0x45,0x9f,0x33;
dword privateKeySize = elcount(privateKey);
byte data[3] = {0x11, 0x11, 0x11};
dword dataSize = elcount(data);
byte signature[1000];
dword signatureSize = elcount(signature);
long result;
result = SecurityLocalSignEcdsa(curve, hashAlgorithm, signatureFormat, privateKey, privateKeySize, data, dataSize, signature, signatureSize);
```

[SecurityLocalVerifyEd25519](CAPLfunctionSecurityLocalVerifyEd25519.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
