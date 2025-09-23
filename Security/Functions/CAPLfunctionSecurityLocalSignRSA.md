# SecurityLocalSignRSA

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalSignRSA

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

`SecurityLocalSignRSA(byte privateKey[], dword privateKey Length, byte data[], dword dataLength, byte signature[], dword* signatureLength, dword signatureScheme)`

## Description

Generates signature of data with a given private key using asymmetric RSA signature algorithm. Signing scheme can be selected via the parameter.

## Parameters

- **privateKey**: The private key to be used for signing
- **privateKeyLength**: Length of the private key to be used for signing
- **data**: Data to be signed
- **dataLength**: Length of the data to be signed
- **signature [OUT]**: Generated signature
- **signatureLength [IN/OUT]**: Length of generated signature
- **signatureScheme**:
  - PKCS1_v1_5_SHA-256 = 1
  - PKCS1_v1_5_SHA-384 = 2
  - PKCS1_v1_5_SHA-512 = 3
  - SSA_PSS_SHA-256 = 4
  - SSA_PSS_SHA-384 = 5
  - SSA_PSS_SHA-512 = 6

## Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **\<= 0**: Error. A value less than or equal to 0 means error.

## Example

```plaintext
byte privateKey[1794] = {0x30, … , 0x60};
dword privateKeyLength = elcount(privateKey);
byte plainData[30] = {0x42, …, 0x42};
dword plainDataLength = elcount(plainData);
byte signature[1000];
dword signatureLength = elcount(signature);
dword signatureScheme = 1;
long result;

result = SecurityLocalSignRSA(privateKey, privateKeyLength, plainData, plainDataLength, signature, signatureLength, signatureScheme);
```

[SecurityLocalDecryptRsa](CAPLfunctionSecurityLocalDecryptRsa.md) • [SecurityLocalEncryptRsa](CAPLfunctionSecurityLocalEncryptRsa.md) • [SecurityLocalVerifyRsa](CAPLfunctionSecurityLocalVerifyRSA.md)
