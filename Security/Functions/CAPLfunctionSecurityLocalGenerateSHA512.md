[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalGenerateSHA512.md)

## SecurityLocalGenerateSHA512

**CAPL Functions** » **Security** » SecurityLocalGenerateSHA512

### Valid for:
- CANoe DE
- CANoe4SW DE

### Note
Replaces LocalSecurityGenerateSHA512.

### Function Syntax

```c
long SecurityLocalGenerateSHA512(byte data[], dword dataLength, byte sha512[], dword sha512Length)
```

### Description
Generates a SHA512 hash for the given data and using the given key.

### Parameters

- **byte data[]**: The data to encrypt.
- **dword dataLength**: The length of the data to encrypt.
- **byte sha512[] [Out]**: The generated SHA512 hash.
- **dword sha512Length [In/Out]**: The length of the generated SHA512 hash (64 bytes).

### Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **\<= 0**: Error. A value less than or equal to 0 means error.

### Example

```c
byte data[3] = { 0x61, 0x62, 0x63 };
byte refOutput[64] ={
  0xdd, 0xaf, 0x35, 0xa1, 0x93, 0x61, 0x7a, 0xba,
  0xcc, 0x41, 0x73, 0x49, 0xae, 0x20, 0x41, 0x31,
  0x12, 0xe6, 0xfa, 0x4e, 0x89, 0xa9, 0x7e, 0xa2,
  0x0a, 0x9e, 0xee, 0xe6, 0x4b, 0x55, 0xd3, 0x9a,
  0x21, 0x92, 0x99, 0x2a, 0x27, 0x4f, 0xc1, 0xa8,
  0x36, 0xba, 0x3c, 0x23, 0xa3, 0xfe, 0xeb, 0xbd,
  0x45, 0x4d, 0x44, 0x23, 0x64, 0x3c, 0xe8, 0x0e,
  0x2a, 0x9a, 0xc9, 0x4f, 0xa5, 0x4c, 0xa4, 0x9f
};

dword refOutputLength = 64;
byte output[64];
dword outputLength = 64;
dword result = 255;
dword counter = 0;
result = SecurityLocalGenerateSHA512(data, elCount(data), output, outputLength);
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
