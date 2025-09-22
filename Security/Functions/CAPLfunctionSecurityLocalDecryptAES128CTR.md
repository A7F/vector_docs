[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDecryptAES128CTR.md)

## SecurityLocalDecryptAES128CTR

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalDecryptAES128CTR

**Valid for:** CANoe DE • CANoe4SW DE

### Function Syntax

```
long SecurityLocalDecryptAES128CTR(byte key[], dword keyLength, byte cipheredData[], dword cipheredDataLength, byte initVector[], dword initVectorLength, byte plainData[], dword plainDataLength)
```

### Description

Decrypts ciphered data with a given key and initialization vector using AES128 (CTR), Padding Mode is not required.

### Parameters

- **byte key[]**: The key to be used for AES (128 bit).
- **dword keyLength**: 16 (bytes).
- **byte cipheredData[]**: The ciphered data to decrypt.
- **dword cipheredDataLength**: The length of the ciphered data.
- **byte initVector[]**: The init vector to be used.
- **dword initVectorLength**: 16 (bytes).
- **byte plainData[] [Out]**: The buffer in which the plain data is stored.
- **dword plainDataLength [In/Out]**: The length of the buffer for the plain data. Typically this buffer should have the same length as the ciphered data buffer.

### Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **\<= 0**: Error. A value less than or equal to 0 means error.

### Example

```c
byte keyData[16] = {0x2b, 0x7e, 0x15, 0x16, 0x28, 0xae, 0xd2, 0xa6, 0xab, 0xf7, 0x15, 0x88, 0x09, 0xcf, 0x4f, 0x3c};
dword keyLength = elcount(keyData);
byte cipheredData[64] = {0x87, 0x4d, 0x61, 0x91, 0xb6, 0x20, 0xe3, 0x26, 0x1b, 0xef, 0x68, 0x64, 0x99, 0x0d, 0xb6, 0xce, 0x98, 0x06, 0xf6, 0x6b, 0x79, 0x70, 0xfd, 0xff, 0x86, 0x17, 0x18, 0x7b, 0xb9, 0xff, 0xfd, 0xff, 0x5a, 0xe4, 0xdf, 0x3e, 0xdb, 0xd5, 0xd3, 0x5e, 0x5b, 0x4f, 0x09, 0x02, 0x0d, 0xb0, 0x3e, 0xab, 0x1e, 0x03, 0x1d, 0xda, 0x2f, 0xbe, 0x03, 0xd1, 0x79, 0x21, 0x70, 0xa0, 0xf3, 0x00, 0x9c, 0xee};
dword cipheredDataLength = elcount(cipheredData);
byte initVector[16] = {0xf0, 0xf1, 0xf2, 0xf3, 0xf4, 0xf5, 0xf6, 0xf7, 0xf8, 0xf9, 0xfa, 0xfb, 0xfc, 0xfd, 0xfe, 0xff};
dword initVectorLength = elcount(initVector);
byte plainOutput[64];
dword plainOutputLength = elcount(plainOutput);

long result;

result = SecurityLocalDecryptAES128CTR(keyData, keyLength, cipheredData, cipheredDataLength, initVector, initVectorLength, plainOutput, plainOutputLength);
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
