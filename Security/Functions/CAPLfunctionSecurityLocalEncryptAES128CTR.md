[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalEncryptAES128CTR.md)

# SecurityLocalEncryptAES128CTR

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalEncryptAES128CTR

Valid for:  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalEncryptAES128CTR(byte key[], dword keyLength, byte data[], dword dataLength, byte initVector[], dword initVectorLength, byte cipheredData[], dword cipheredDataLength)
```

## Description

Encrypts data with a given key and initialization vector using AES128 (CTR), Padding Mode is not required.

## Parameters

- **byte key[]**: The key to be used for AES (128 bit).
- **dword keyLength**: 16 (bytes).
- **byte data[]**: The data to encrypt.
- **dword dataLength**: The length of the data to encrypt.
- **byte initVector[]**: The init vector to be used.
- **dword initVectorLength**: 16 (bytes).
- **byte cipheredData [] [Out]**: The buffer in which the ciphered data is stored.
- **dword cipheredDataLength [In/Out]**: The length of the buffer. Typically this buffer should have the same length as the data to encrypt.

## Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[16] = {0x2b, 0x7e, 0x15, 0x16, 0x28, 0xae, 0xd2, 0xa6, 0xab, 0xf7, 0x15, 0x88, 0x09, 0xcf, 0x4f, 0x3c};
dword keyLength = elcount(keyData);
byte data[64] = {0x6b, 0xc1, 0xbe, 0xe2, 0x2e, 0x40, 0x9f, 0x96, 0xe9, 0x3d, 0x7e, 0x11, 0x73, 0x93, 0x17, 0x2a, 0xae, 0x2d, 0x8a, 0x57, 0x1e, 0x03, 0xac, 0x9c, 0x9e, 0xb7, 0x6f, 0xac, 0x45, 0xaf, 0x8e, 0x51, 0x30, 0xc8, 0x1c, 0x46, 0xa3, 0x5c, 0xe4, 0x11, 0xe5, 0xfb, 0xc1, 0x19, 0x1a, 0x0a, 0x52, 0xef, 0xf6, 0x9f, 0x24, 0x45, 0xdf, 0x4f, 0x9b, 0x17, 0xad, 0x2b, 0x41, 0x7b, 0xe6, 0x6c, 0x37, 0x10};
dword dataLength = elcount(data);
byte initVector[16] = {0xf0, 0xf1, 0xf2, 0xf3, 0xf4, 0xf5, 0xf6, 0xf7, 0xf8, 0xf9, 0xfa, 0xfb, 0xfc, 0xfd, 0xfe, 0xff};
dword initVectorLength = elcount(initVector);
byte cipheredOutput[64];
dword cipheredOutputLength = elcount(cipheredOutput);

long result;

result = SecurityLocalEncryptAES128CTR(keyData, keyLength, data, dataLength, initVector, initVectorLength, cipheredOutput, cipheredOutputLength);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)