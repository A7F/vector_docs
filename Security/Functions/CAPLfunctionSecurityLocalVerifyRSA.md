[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalVerifyRSA.md)

# SecurityLocalVerifyRSA

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalVerifyRSA

Valid for: CANoe DE • CANoe4SW DE

## Function Syntax

`SecurityLocalVerifyRSA(byte publicKey[], dword publicKeyLength, byte data[], dword dataLength, byte signature[], dword signatureLength, dword signatureScheme, dword* verificationResult)`

## Description

Verifies signature of data with a given public key using asymmetric RSA signature algorithm. Signing scheme can be selected via the parameter.

## Parameters

- **publicKey**: The public key to be used for verification.
- **publicKeyLength**: Length of the public key to be used for verification.
- **data**: Data to be verified.
- **dataLength**: Length of the data to be verified.
- **signature**: Signature to be verified.
- **signatureLength**: Length of signature to be verified.
- **signatureScheme**:
  - PKCS1_v1_5_SHA-256 = 1
  - PKCS1_v1_5_SHA-384 = 2
  - PKCS1_v1_5_SHA-512 = 3
  - SSA_PSS_SHA-256 = 4
  - SSA_PSS_SHA-384 = 5
  - SSA_PSS_SHA-512 = 6
- **verificationResult [OUT]**: Result of the signature verification.

## Return Values

- **1**: Success. A value of 1 means that the action was successful. Note: This does not necessarily mean that the signature is valid. Check VerificationResult therefore!
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```plaintext
byte plainData[30] = {0x42, …, 0x42};
dword plainDataLength = elcount(plainData);
byte signature[1000] = {0xAA, ..., 0xAA};
dword signatureLength = elcount(signature);
dword signatureScheme = 1;

long result;

byte pubKey[634] = {0x2D, …, 0x2D};
dword pubKeyLength = elcount(pubKey);
dword verificationResult;

result = SecurityLocalVerifyRSA(pubKey, pubKeyLength, plainData, plainDataLength, signature, signatureLength, signatureScheme, verificationResult);
```

[SecurityLocalDecryptRsa](CAPLfunctionSecurityLocalDecryptRsa.md) • [SecurityLocalEncryptRsa](CAPLfunctionSecurityLocalEncryptRsa.md) • [SecurityLocalSignRsa](CAPLfunctionSecurityLocalSignRSA.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
