[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalEncryptAES192GCM.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalEncryptAES192GCM

# SecurityLocalEncryptAES192GCM

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SecurityLocalEncryptAES192GCM(byte key[], dword keyLength, byte iv[], dword ivLength, byte aad[], dword aadLength, byte plainData[], dword plainDataLength, byte tag[], dword tagLength, byte cipheredData[], dword cipheredDataLength);
```

## Description

Encrypts data with a given key, initialization vector and additional authenticated data. The encryption is AES192 (GCM). Also stores tag in separate buffer.

## Parameters

- **byte key[]**: The key to be used for AES (24 bytes)
- **dword keyLength**: 24 (bytes)
- **byte iv[]**: The init vector
- **dword ivLength**: The length of the init vector
- **byte aad[]**: The additional authenticated data
- **dword aadLength**: The length of the additional authenticated data
- **byte plainData[]**: The data to encrypt
- **dword plainDataLength**: The length of the data
- **byte tag[][out]**: The buffer where to store the verification tag for the ciphered text
- **dword tagLength**: 16 (bytes)
- **byte cipheredData[][out]**: The buffer in which the ciphered data is stored.
- **dword cipheredDataLength [in/out]**: The length of the buffer. Typically, this buffer should have the same length as the data to encrypt.

## Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **≤ 0**: Error. A value less than or equal to 0 means error.

## Example

```plaintext
byte keyData[24] = {0xfe, 0xff, 0xe9, 0x92, 0x86, 0x65, 0x73, 0x1c, 0x6d, 0x6a, 0x8f, 0x94, 0x67, 0x30, 0x83, 0x08, 0xfe, 0xff, 0xe9, 0x92, 0x86, 0x65, 0x73, 0x1c};
dword keyLength = elcount(keyData);
byte plainText[60] = {0xd9, 0x31, 0x32, 0x25, 0xf8, 0x84, 0x06, 0xe5, 0xa5, 0x59, 0x09, 0xc5, 0xaf, 0xf5, 0x26, 0x9a, 0x86, 0xa7, 0xa9, 0x53, 0x15, 0x34, 0xf7, 0xda, 0x2e, 0x4c, 0x30, 0x3d, 0x8a, 0x31, 0x8a, 0x72, 0x1c, 0x3c, 0x0c, 0x95, 0x95, 0x68, 0x09, 0x53, 0x2f, 0xcf, 0x0e, 0x24, 0x49, 0xa6, 0xb5, 0x25, 0xb1, 0x6a, 0xed, 0xf5, 0xaa, 0x0d, 0xe6, 0x57, 0xba, 0x63, 0x7b, 0x39};
dword plainTextLength = elcount(plainText);
byte initVector[12] = {0xca, 0xfe, 0xba, 0xbe, 0xfa, 0xce, 0xdb, 0xad, 0xde, 0xca, 0xf8, 0x88};
dword initVectorLength = elcount(initVector);
byte cipheredData[76];
dword cipheredDataLength = elcount(cipheredData);
byte aad[20] = {0xfe, 0xed, 0xfa, 0xce, 0xde, 0xad, 0xbe, 0xef, 0xfe, 0xed, 0xfa, 0xce, 0xde, 0xad, 0xbe, 0xef, 0xab, 0xad, 0xda, 0xd2};
dword aadLength = elcount(aad);
long result;
byte tag[16] = {0x25, 0x19, 0x49, 0x8e, 0x80, 0xf1, 0x47, 0x8f, 0x37, 0xba, 0x55, 0xbd, 0x6d, 0x27, 0x61, 0x8c};
dword tagLength = elcount(tag);

result = SecurityLocalEncryptAES192GCM(keyData, keyLength, initVector, initVectorLength, aad, aadLength, plainText, plainTextLength, tag, tagLength, cipheredData, cipheredDataLength);
```

[SecurityLocalEncryptAES128GCM](CAPLfunctionSecurityLocalEncryptAES128GCM.md) • [SecurityLocalEncryptAES256GCM](CAPLfunctionSecurityLocalEncryptAES256GCM.md) • [SecurityLocalDecryptAES192GCM](CAPLfunctionSecurityLocalDecryptAES192GCM.md)

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
