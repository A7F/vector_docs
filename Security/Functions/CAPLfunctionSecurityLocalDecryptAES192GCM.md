[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDecryptAES192GCM.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalDecryptAES192GCM

# SecurityLocalDecryptAES192GCM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalDecryptAES192GCM(byte key[], dword keyLength, byte iv[], dword ivLength, byte aad[], dword aadLength, byte cipheredData[], dword cipheredDataLength, byte tag[], dword tagLength, byte plainData[], dword plainDataLength)
```

## Description

Decrypts ciphered data with a given key, initialization vector and additional authenticated data. The decryption is AES192 (GCM). Also verifies result with tag.

## Parameters

- **byte key[]**: The key to be used for AES (192 bit)
- **dword keyLength**: 24 (bytes)
- **byte iv[]**: The init vector
- **dword ivLength**: The length of the init vector
- **byte aad[]**: The additional authenticated data
- **dword aadLength**: The length of the additional authenticated data
- **byte cipheredData[]**: The ciphered data to decrypt
- **dword cipheredDataLength**: The length of the ciphered data
- **byte tag[]**: The verification tag for the ciphered text
- **dword tagLength**: The length of the verification tag, must equal 16
- **byte plainData[] [out]**: The buffer in which the plain data is stored
- **dword plainDataLength [in/out]**: The length of the buffer. Typically, this buffer should have the same length as the ciphered data buffer

## Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **≤ 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[24] = {0xfe, 0xff, 0xe9, 0x92, 0x86, 0x65, 0x73, 0x1c, 0x6d, 0x6a, 0x8f, 0x94, 0x67, 0x30, 0x83, 0x08, 0xfe, 0xff, 0xe9, 0x92, 0x86, 0x65, 0x73, 0x1c};
dword keyLength = elcount(keyData);
byte iv[12] = {0xca, 0xfe, 0xba, 0xbe, 0xfa, 0xce, 0xdb, 0xad, 0xde, 0xca, 0xf8, 0x88};
dword ivLength = elcount(iv);
byte aad[20] = {0xfe, 0xed, 0xfa, 0xce, 0xde, 0xad, 0xbe, 0xef, 0xfe, 0xed, 0xfa, 0xce, 0xde, 0xad, 0xbe, 0xef, 0xab, 0xad, 0xda, 0xd2};
dword aadLength = elcount(aad);
byte cipheredText[60] = {0x39, 0x80, 0xca, 0x0b, 0x3c, 0x00, 0xe8, 0x41, 0xeb, 0x06, 0xfa, 0xc4, 0x87, 0x2a, 0x27, 0x57, 0x85, 0x9e, 0x1c, 0xea, 0xa6, 0xef, 0xd9, 0x84, 0x62, 0x85, 0x93, 0xb4, 0x0c, 0xa1,
0xe1, 0x9c, 0x7d, 0x77, 0x3d, 0x00, 0xc1, 0x44, 0xc5, 0x25, 0xac, 0x61, 0x9d, 0x18, 0xc8, 0x4a, 0x3f, 0x47, 0x18, 0xe2, 0x44, 0x8b, 0x2f, 0xe3, 0x24, 0xd9, 0xcc, 0xda, 0x27, 0x10};
dword cipheredTextLength = elcount(cipheredText);
byte tag[16] = {0x25, 0x19, 0x49, 0x8e, 0x80, 0xf1, 0x47, 0x8f, 0x37, 0xba, 0x55, 0xbd, 0x6d, 0x27, 0x61, 0x8c};
dword tagLength = elcount(tag);
byte plainText[100];
dword plainTextLength = elcount(plainText);
long result;
result =  SecurityLocalDecryptAES192GCM(keyData, keyLength, iv, ivLength, aad, aadLength, cipheredText, cipheredTextLength, tag, tagLength, plainText, plainTextLength);
```

[SecurityLocalEncryptAES128GCM](CAPLfunctionSecurityLocalEncryptAES128GCM.md) • [SecurityLocalDecryptAES256GCM](CAPLfunctionSecurityLocalDecryptAES256GCM.md) • [SecurityLocalEncryptAES192GCM](CAPLfunctionSecurityLocalEncryptAES192GCM.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
