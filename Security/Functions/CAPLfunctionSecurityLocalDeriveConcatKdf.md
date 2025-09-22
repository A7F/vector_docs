[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalDeriveConcatKdf.md)

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalDeriveConcatKdf

# SecurityLocalDeriveConcatKdf

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```
long SecurityLocalDeriveConcatKdf(dword hashAlgorithm, byte secret[], dword secretLength, byte label[], dword labelLength, dword keyLength, byte outputKey[] [OUT]);
```

## Description

Derive a key using the Concatenation KDF (NIST SP 800-56A).

This is the Concatenation Key Derivation Function as defined in [section 5.8.1 of NIST SP 800-56A Rev. 1](https://csrc.nist.gov/pubs/sp/800/56/a/r1/final).

It is the same as the One-step Key Derivation as defined in [section 5.8.2.1 of NIST SP 800-56A Rev. 3](https://csrc.nist.gov/pubs/sp/800/56/a/r3/final) with the Concatenation Format for FixedInfo (section 5.8.2.1.1), if the one-step key-derivation method specified in SP 800-56C is used with H = hash.

Note that it is upon the user to ensure that the provided label satisfies the requirements from NIST SP 800-56A.

## Parameters

- **dword hashAlgorithm**  
  ID of the hash algorithm to use.  
  Available hash algorithm:  
  - SHA-256 = 1
  - SHA-384 = 2
  - SHA-512 = 3
  - SHA-224 = 4
  - SM3 = 5

- **byte secret[]**  
  The secret to derive the key from.

- **dword secretLength**  
  The length of the secret.

- **byte label[]**  
  A string identifying the purpose of the derived key (also called OtherInfo or FixedInfo).

- **dword labelLength**  
  The length of the label.

- **dword keyLength**  
  The length of the key to derive.

- **byte outputKey[] [OUT]**  
  Output buffer for the derived key.

## Return Values

- **1**  
  Success. A value of 1 means that the action was successful.

- **\<= 0**  
  Error. A value less than or equal to 0 means error.

## Example

```c
dword hashAlgorithm = 1; // SHA-256
byte secret[16] = {0xE3, 0xC0, 0x8A, 0x8F, 0x06, 0xC6, 0xE3, 0xAD, 0x95, 0xA7, 0x05, 0x57, 0xB2, 0x3F, 0x75, 0x48};
byte label[3] = {0x01, 0x55, 0x56};
byte derivedKey[16];
long result;
result = SecurityLocalDeriveConcatKdf(hashAlgorithm, secret, elCount(secret), label, elCount(label), elCount(derivedKey), derivedKey);
```

[SecurityLocalSignRsa](CAPLfunctionSecurityLocalSignRSA.md) • [SecurityLocalEncryptRsa](CAPLfunctionSecurityLocalEncryptRsa.md) • [SecurityLocalVerifyRsa](CAPLfunctionSecurityLocalVerifyRSA.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
