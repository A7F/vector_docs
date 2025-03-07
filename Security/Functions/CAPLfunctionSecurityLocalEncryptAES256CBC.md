[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalEncryptAES256CBC.md)

# SecurityLocalEncryptAES256CBC

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalEncryptAES256CBC

**Valid for:** CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalEncryptAES256CBC(byte key[], dword keyLength, byte data[], dword dataLength, byte initVector[], dword initVectorLength, byte cipheredData[], dword cipheredDataLength)
```

## Description

Encrypts data with a given key and initialization vector using AES256 (CBC), Padding Mode PKCS5.

## Parameters

- **byte key[]**: The key to be used for AES (256 bit).
- **dword keyLength**: 32 (bytes).
- **byte data[]**: The data to encrypt.
- **dword dataLength**: The length of the data to encrypt.
- **byte initVector[]**: The init vector to be used.
- **dword initVectorLength**: 16 (bytes).
- **byte cipheredData [] [Out]**: The buffer in which the ciphered data is stored.
- **dword cipheredData Length [In/Out]**: The length of the buffer. Typically this buffer has to be 16 bytes longer than the length of the data to encrypt.

## Return Values

- **1**: Success. A Value of 1 means that the action was successful.
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[32] = {0x73, 0xb8, 0xfa, 0xf0, 0x0b, 0x33, 0x02, 0xac, 0x99, 0x85, 0x5c, 0xf6, 0xf9, 0xe9, 0xe4, 0x85, 0x18, 0x69, 0x0a, 0x59, 0x06, 0xa4, 0x86, 0x9d, 0x4d, 0xcf, 0x48, 0xd2, 0x82, 0xfa, 0xae, 0x2a};
dword keyLength = elcount(keyData);
byte data[80] = {0x3a, 0xde, 0xa6, 0xe0, 0x6e, 0x42, 0xc4, 0xf0, 0x41, 0x02, 0x14, 0x91, 0xf2, 0x77, 0x5e, 0xf6, 0x37, 0x8c, 0xb0, 0x88, 0x24, 0x16, 0x5e, 0xdc, 0x4f, 0x64, 0x48, 0xe2, 0x32, 0x17, 0x5b, 0x60, 0xd0, 0x34, 0x5b, 0x9f, 0x9c, 0x78, 0xdf, 0x65, 0x96, 0xec, 0x9d, 0x22, 0xb7, 0xb9, 0xe7, 0x6e, 0x8f, 0x3c, 0x76, 0xb3, 0x2d, 0x5d, 0x67, 0x27, 0x3f, 0x1d, 0x83, 0xfe, 0x7a, 0x6f, 0xc3, 0xdd, 0x3c, 0x49, 0x13, 0x91, 0x70, 0xfa, 0x57, 0x01, 0xb3, 0xbe, 0xac, 0x61, 0xb4, 0x90, 0xf0, 0xa9};
dword dataLength = elcount(data);
byte initVector[16] = {0xb3, 0xcb, 0x97, 0xa8, 0x0a, 0x53, 0x99, 0x12, 0xb8, 0xc2, 0x1f, 0x45, 0x0d, 0x3b, 0x93, 0x95};
dword initVectorLength = elcount(initVector);
byte cipheredOutput[96];
dword cipheredOutputLength = elcount(cipheredOutput);

long result;

result = SecurityLocalEncryptAES256CBC(keyData, keyLength, data, dataLength, initVector, initVectorLength, cipheredOutput, cipheredOutputLength);
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)