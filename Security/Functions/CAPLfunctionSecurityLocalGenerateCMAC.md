[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGenerateCMAC.md)

**CAPL Functions** » **Security** » **SecurityLocalGenerateCMAC**

# SecurityLocalGenerateCMAC

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

**Note**  
Replaces `LocalSecurityGenerateCMAC`.

## Function Syntax

```
long SecurityLocalGenerateCMAC(byte key[], dword keyLength, byte data[], dword dataLength, byte cmac[], dword cmacLength)
```

## Description

Generates a hash for the given data and key. The generated hash is a CMAC.

## Parameters

- **byte key[]**: The key to be used.
- **dword keyLength**: 16 or 32 (bytes).
- **byte data[]**: The data for which the CMAC should be computed.
- **dword dataLength**: The length of the data for which the CMAC should be computed.
- **byte cmac[] [Out]**: The generated CMAC.
- **dword cmacLength [In/Out]**: The length of the generated CMAC (16 bytes).

## Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.
- **≤ 0**: Error  
  A value less than or equal to 0 means error.

## Example

**Example**  

```plaintext
byte keyData[16] = {0x2b, 0x7e, 0x15, 0x16, 0x28, 0xae, 0xd2, 0xa6, 0xab, 0xf7, 0x15, 0x88, 0x09, 0xcf, 0x4f, 0x3c};
dword keyLength = elcount(keyData);
byte data[16] = {0x6b, 0xc1, 0xbe, 0xe2, 0x2e, 0x40, 0x9f, 0x96, 0xe9, 0x3d, 0x7e, 0x11, 0x73, 0x93, 0x17, 0x2a};
dword dataLength = elcount(data);
byte cmac[16];
dword cmacLength = elcount(cmac);

long result;

result = SecurityLocalGenerateCMAC(keyData, keyLength, data, dataLength, cmac, cmacLength);
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
