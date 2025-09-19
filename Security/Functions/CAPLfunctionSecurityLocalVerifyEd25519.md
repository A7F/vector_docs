[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionSecurityLocalVerifyEd25519.md)

# SecurityLocalVerifyEd25519

[CAPL Functions](../../CAPLfunctions.md) » [Security](../CAPLFunctionsSecurityOverview.md) » SecurityLocalVerifyEd25519

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

`SecurityLocalVerifyEd25519(byte[] PublicKey, dword PublicKeyLength, byte[] Data, dword DataLength, byte[] Signature, dword SignatureLength, dword& VerificationResult)`

## Description

Verifies signature of data signed with Ed25519 signing algorithm.

## Parameters

- **publicKey**: The public key to be used for verification.
- **publicKeyLength**: Size of Public key to be used for signature verification. Expected size is 32 bytes for Ed25519.
- **data**: Buffer containing the data to be verified.
- **dataLength**: Size of the buffer to be verified. Maximum size is 65536 bytes.
- **signature**: Buffer containing the signature.
- **signatureLength**: Length of the signature, expected size is 64 bytes.
- **verificationResult [OUT]**: Result of the signature verification.

## Return Values

- **1**: Success. A value of 1 means that the action was successful.
- **<= 0**: Error. A value less than or equal to 0 means error.

## Example

```plaintext
byte priv[1000];
byte pub[1000];
byte data[1000];
byte signature[64];
dword verify;

dword privSize;
dword pubSize;
dword dataSize;
dword signatureSize;

privSize = elcount(priv);
pubSize = elcount(pub);
dataSize = elcount(data);
signatureSize = elcount(signature);

verify = 0;

write("SecurityLocalGenerateAsymmetricKeyPair Ed25519");
SecurityLocalGenerateAsymmetricKeyPair(1, priv, privSize, pub, pubSize);

SecurityLocalSignEd25519(priv, privSize, data, dataSize, signature, signatureSize);
SecurityLocalVerifyEd25519(pub, pubSize, data, dataSize, signature, signatureSize, verify);

write("VerificationResult result %ld", verify);
```

[SecurityLocalSignEd25519](CAPLfunctionSecurityLocalSignEd25519.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
