[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDecryptAES256CBC.md)

**CAPL Functions** » **Security** » **SecurityLocalDecryptAES256CBC**

# SecurityLocalDecryptAES256CBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalDecryptAES256CBC(byte key[], dword keyLength, byte cipheredData[], dword cipheredDataLength, byte initVector[], dword initVectorLength, byte plainData[], dword plainDataLength)
```

## Description

Decrypts ciphered data with a given key and initialization vector using AES256 (CBC), Padding Mode PKCS5.

## Parameters

- **byte key[]**: The key to be used for AES (256 bit).
- **dword keyLength**: 32 (bytes).
- **byte cipheredData[]**: The ciphered data to decrypt.
- **dword cipheredDataLength**: The length of the ciphered data.
- **byte initVector[]**: The init vector to be used.
- **dword initVectorLength**: 16 (bytes).
- **byte plainData[] [Out]**: The buffer in which the plain data is stored.
- **dword plainDataLength [In/Out]**: The length of the buffer for the plain data. Typically this buffer should have the same length as the ciphered data buffer.

## Return Values

- **1**: Success. A Value of 1 means that the action was successful.
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[32] = {0x73, 0xb8, 0xfa, 0xf0, 0x0b, 0x33, 0x02, 0xac, 0x99, 0x85, 0x5c, 0xf6, 0xf9, 0xe9, 0xe4, 0x85, 0x18, 0x69, 0x0a, 0x59, 0x06, 0xa4, 0x86, 0x9d, 0x4d, 0xcf, 0x48, 0xd2, 0x82, 0xfa, 0xae, 0x2a};
dword keyLength = elcount(keyData);
byte cipheredData[96] = {0xac, 0x3d, 0x6d, 0xba, 0xfe, 0x2e, 0x0f, 0x74, 0x06, 0x32, 0xfd, 0x9e, 0x82, 0x0b, 0xf6, 0x04, 0x4c, 0xd5, 0xb1, 0x55, 0x1c, 0xbb, 0x9c, 0xc0, 0x3c, 0x0b, 0x25, 0xc3, 0x9c, 0xcb, 0x7f, 0x33, 0xb8, 0x3a, 0xac, 0xfc, 0xa4, 0x0a, 0x32, 0x65, 0xf2, 0xbb, 0xff, 0x87, 0x91, 0x53, 0x44, 0x8a, 0xca, 0xcb, 0x88, 0xfc, 0xfb, 0x3b, 0xb7, 0xb1, 0x0f, 0xe4, 0x63, 0xa6, 0x8c, 0x01, 0x09, 0xf0, 0x28, 0x38, 0x2e, 0x3e, 0x55, 0x7b, 0x1a, 0xdf, 0x02, 0xed, 0x64, 0x8a, 0xb6, 0xbb, 0x89, 0x5d, 0x74, 0xc8, 0xd8, 0x46, 0x51, 0x0b, 0xf9, 0xcc, 0x08, 0xe2, 0x08, 0x81, 0xc5, 0xe3, 0xe3, 0x96};
dword cipheredDataLength = elcount(cipheredData);
byte initVector[16] = {0xb3, 0xcb, 0x97, 0xa8, 0x0a, 0x53, 0x99, 0x12, 0xb8, 0xc2, 0x1f, 0x45, 0x0d, 0x3b, 0x93, 0x95};
dword initVectorLength = elcount(initVector);
byte plainOutput[96];
dword plainOutputLength = elcount(plainOutput);

long result;

result = SecurityLocalDecryptAES256CBC(keyData, keyLength, cipheredData, cipheredDataLength, initVector, initVectorLength, plainOutput, plainOutputLength);
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions)** Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
