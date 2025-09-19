[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGenerateHashMACSHA256.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalGenerateHashMACSHA256

# SecurityLocalGenerateHashMACSHA256

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
`long SecurityLocalGenerateHashMACSHA256(byte key[], dword keyLength, byte data[], dword dataLength, byte* hashMac)`
```

## Description

Generates a SHA256 hash for the given data, using the given key.

## Parameters

- **byte key[]**: The key to be used.
- **dword keyLength**: 16 (bytes).
- **byte data[]**: The data to encrypt.
- **dword dataLength**: The length of the data to encrypt.
- **byte* hashMac[Out]**: The generated SHA256 hash MAC.

## Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.
- **<= 0**: Error  
  A value less than or equal to 0 means error.

## Example

```c
byte key[16] = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};

byte data[16] = { 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00, 0x00};

byte refOutput[32] = {0x85, 0x3C, 0x74, 0x03, 0x93, 0x7D, 0x8B, 0x62, 0x39, 0x56, 0x9B, 0x18, 0x4E, 0xB7, 0x99, 0x3F, 0xC5, 0xF7, 0x51, 0xAE, 0xFC, 0xEA, 0x28, 0xF2, 0xC8, 0x63, 0x85, 0x8E, 0x2D, 0x29, 0xC5, 0x0B};

dword refOutputLength = 32;
byte output[32];
dword result = 255;
result = SecurityLocalGenerateHashMACSHA256(key, elCount(key), data, elCount(data), output);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)