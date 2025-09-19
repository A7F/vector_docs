[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDecryptAES128GCM.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalDecryptAES128GCM

# SecurityLocalDecryptAES128GCM

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalDecryptAES128GCM(byte key[], dword keyLength, byte iv[], dword ivLength, byte aad[], dword aadLength, byte cipheredData[], dword cipheredDataLength, byte tag[], dword tagLength, byte plainData[], dword plainDataLength)
```

## Description

Decrypts ciphered data with a given key, initialization vector and additional authentication data. The decryption is AES128 (GCM). Also verifies result with tag.

## Parameters

- **byte key[]**: The key to be used for AES (128 bit)
- **dword keyLength**: 16 (bytes)
- **byte iv[]**: The init vector
- **dword ivLength**: The length of the init vector
- **byte aad[]**: The additional authentication data
- **dword aadLength**: The length of the additional authentication data
- **byte cipheredData[]**: Ciphered data to decrypt
- **dword cipheredDataLength**: The length of the ciphered data
- **byte tag[]**: The verification tag for the ciphered text
- **dword tagLength**: The length of the verification tag, must equal 16
- **byte plainData[] [out]**: The buffer in which the plain data is stored
- **dword plainDataLength [in/out]**: The length of the buffer. Typically this buffer should have the same length as the ciphered data buffer

## Return Values

- **1**: Success. A Value of 1 means that the action was successful.
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[16] = {0xE3, 0xC0, 0x8A, 0x8F, 0x06, 0xC6, 0xE3, 0xAD, 0x95, 0xA7, 0x05, 0x57, 0xB2, 0x3F, 0x75, 0x48};
byte initVector[12] = {0x12, 0x15, 0x35, 0x24, 0xC0, 0x89, 0x5E, 0x81, 0xB2, 0xC2, 0x84, 0x65};
byte aad[70] = {0xD6, 0x09, 0xB1, 0xF0, 0x56, 0x63, 0x7A, 0x0D, 0x46, 0xDF, 0x99, 0x8D, 0x88, 0xE5, 0x22, 0x2A,
0xB2, 0xC2, 0x84, 0x65, 0x12, 0x15, 0x35, 0x24, 0xC0, 0x89, 0x5E, 0x81, 0x08, 0x00, 0x0F, 0x10,
0x11, 0x12, 0x13, 0x14, 0x15, 0x16, 0x17, 0x18, 0x19, 0x1A, 0x1B, 0x1C, 0x1D, 0x1E, 0x1F, 0x20,
0x21, 0x22, 0x23, 0x24, 0x25, 0x26, 0x27, 0x28, 0x29, 0x2A, 0x2B, 0x2C, 0x2D, 0x2E, 0x2F, 0x30,
0x31, 0x32, 0x33, 0x34, 0x00, 0x01 };
// New plain text input
byte plainText[32] = {0x08, 0x00, 0x0F, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16, 0x17, 0x18, 0x19, 0x1A, 0x1B, 0x1C, 0x1D, 0x1E, 0x1F, 0x20, 0x21, 0x22, 0x23, 0x24, 0x25, 0x26, 0x27, 0x28, 0x29, 0x2A, 0x2B, 0x2C};
dword plainLength = elcount(plainText);

byte cipheredText [48]; // Length must be plainLength + 16

byte tag [16] = {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};

byte refTag [16] = {0x2F, 0x0B, 0xC5, 0xAF, 0x40, 0x9E, 0x06, 0xD6, 0x09, 0xEA, 0x8B, 0x7D, 0x0F, 0xA5, 0xEA, 0x50};

byte plainTextOutput [48]; // Must be same length as ciphered text

dword tagLength = elcount(tag);
dword cipheredTextLength = elcount(cipheredText);
dword plainTextOutputLength = elcount(plainTextOutput);

long encryptResult;
long decryptResult;

encryptResult = SecurityLocalEncryptAES128GCM(keyData, elcount(keyData), initVector, elcount(initVector), aad, elcount(aad), plainText, elcount(plainText), tag, tagLength, cipheredText, cipheredTextLength);

decryptResult = SecurityLocalDecryptAES128GCM(keyData, elcount(keyData), initVector, elcount(initVector), aad, elcount(aad), cipheredText, cipheredTextLength, tag, tagLength, plainTextOutput, plainTextOutputLength);
```

[SecurityLocalEncryptAES128GCM](CAPLfunctionSecurityLocalEncryptAES128GCM.md) • [SecurityLocalDecryptAES256GCM](CAPLfunctionSecurityLocalDecryptAES256GCM.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
