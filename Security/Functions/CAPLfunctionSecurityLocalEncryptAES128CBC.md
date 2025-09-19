[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalEncryptAES128CBC.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalEncryptAES128CBC

# SecurityLocalEncryptAES128CBC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityEncryptAES128CBC`.

## Function Syntax

```c
long SecurityLocalEncryptAES128CBC(byte key[], dword keyLength, byte data[], dword dataLength, byte initVector[], dword initVectorLength, byte cipheredData[], dword cipheredDataLength)
```

## Description

Encrypts data with a given key and initialization vector using AES128 (CBC), Padding Mode PKCS5.

## Parameters

- **byte key[]**: The key to be used for AES (128 bit).
- **dword keyLength**: 16 (bytes).
- **byte data[]**: The data to encrypt.
- **dword dataLength**: The length of the data to encrypt.
- **byte initVector[]**: The init vector to be used.
- **dword initVectorLength**: 16 (bytes).
- **byte cipheredData [] [Out]**: The buffer in which the ciphered data is stored.
- **dword cipheredData Length [In/Out]**: The length of the buffer. Typically this buffer has to be 16 bytes longer than the length of the data to encrypt.

## Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.
- **<= 0**: Error  
  A value less than or equal to 0 means error.

## Example

**Example**  

```c
byte keyData[16] = {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};
dword keyLength = elcount(keyData);
byte data[16] = {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};
dword dataLength = elcount(data);
byte initVector[16] = {0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};
dword initVectorLength = elcount(initVector);
byte cipheredOutput[32];
dword cipheredOutputLength = elcount(cipheredOutput);

long result;

result = SecurityLocalEncryptAES128CBC(keyData, keyLength, data, dataLength, initVector, initVectorLength, cipheredOutput, cipheredOutputLength);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
