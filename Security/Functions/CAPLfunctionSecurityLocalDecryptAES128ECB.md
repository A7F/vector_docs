# SecurityLocalDecryptAES128ECB

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityDecryptAES128ECB`.

## Function Syntax

```
long SecurityLocalDecryptAES128ECB(byte key[], dword keyLength, byte cipheredData[], dword cipheredDataLength, byte plainData[], dword plainDataLength)
```

## Description

Decrypts ciphered data with a given key using AES128 (ECB), Padding Mode PKCS5.

## Parameters

- **byte key[]**: The key to be used for AES (128 bit).
- **dword keyLength**: 16 (bytes).
- **byte cipheredData[]**: The ciphered data to decrypt.
- **dword cipheredDataLength**: The length of the ciphered data.
- **byte plainData[] [Out]**: The buffer in which the plain data is stored.
- **dword plainDataLength [In/Out]**: The length of the buffer for the plain data. Typically this buffer should have the same length as the ciphered data buffer.

## Return Values

- **1**: Success. A Value of 1 means that the action was successful.
- **\<= 0**: Error. A value less than or equal to 0 means error.

## Example

```c
byte keyData[16] = {0x00, 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x0a, 0x0b, 0x0c, 0x0d, 0x0e, 0x0f};
dword keyLength = elcount(keyData);
byte cipheredData[32] = {0x69, 0xc4, 0xe0, 0xd8, 0x6a, 0x7b, 0x04, 0x30, 0xd8, 0xcd, 0xb7, 0x80, 0x70, 0xb4, 0xc5, 0x5a, 0x95, 0x4f, 0x64, 0xf2, 0xe4, 0xe8, 0x6e, 0x9e, 0xee, 0x82, 0xd2, 0x02, 0x16, 0x68, 0x48, 0x99};
dword cipheredDataLength = elcount(cipheredData);
byte plainOutput[32];
dword plainOutputLength = elcount(plainOutput);

long result;

result = SecurityLocalDecryptAES128ECB(keyData, keyLength, cipheredData, cipheredDataLength, plainOutput, plainOutputLength);
```
