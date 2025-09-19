[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDecryptAES128CBC.md)

**CAPL Functions** » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalDecryptAES128CBC

# SecurityLocalDecryptAES128CBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityDecryptAES128CBC`.

## Function Syntax

```c
long SecurityLocalDecryptAES128CBC(byte key[], dword keyLength, byte cipheredData[], dword cipheredDataLength, byte initVector[], dword initVectorLength, byte plainData[], dword plainDataLength)
```

## Description

Decrypts ciphered data with a given key and initialization vector using AES128 (CBC), Padding Mode PKCS5.

## Parameters

- **byte key[]**: The key to be used for AES (128 bit).
- **dword keyLength**: 16 (bytes).
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
byte keyData[16] = {0xc2, 0x86, 0x69, 0x6d, 0x88, 0x7c, 0x9a, 0xa0, 0x61, 0x1b, 0xbb, 0x3e, 0x20, 0x25, 0xa4, 0x5a};
dword keyLength = elcount(keyData);

byte cipheredData[48] = {0xd2, 0x96, 0xcd, 0x94, 0xc2, 0xcc, 0xcf, 0x8a, 0x3a, 0x86, 0x30, 0x28, 0xb5, 0xe1, 0xdc, 0x0a, 0x75, 0x86, 0x60, 0x2d, 0x25, 0x3c, 0xff, 0xf9, 0x1b, 0x82, 0x66, 0xbe, 0xa6, 0xd6, 0x1a, 0xb1, 0xbc, 0xfd, 0x81, 0x02, 0x22, 0x02, 0x36, 0x6b, 0xde, 0x6d, 0xd2, 0x60, 0xa1, 0x58, 0x41, 0xa1};
dword cipheredDataLength = elcount(cipheredData);

byte initVector[16] = {0x56, 0x2e, 0x17, 0x99, 0x6d, 0x09, 0x3d, 0x28, 0xdd, 0xb3, 0xba, 0x69, 0x5a, 0x2e, 0x6f, 0x58};
dword initVectorLength = elcount(initVector);

byte plainOutput[48];
dword plainOutputLength = elcount(plainOutput);

long result;

result = SecurityLocalDecryptAES128CBC(keyData, keyLength, cipheredData, cipheredDataLength, initVector, initVectorLength, plainOutput, plainOutputLength);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
