# SecurityLocalSignEd25519

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

`SecurityLocalSignEd25519(byte[] PrivateKey, dword PrivateKeyLength, byte[] Data, dword DataLength, byte[] Signature, dword& SignatureLength)`

## Description

Generates signature of data with a given private key using asymmetric Ed25519 signature algorithm.

## Parameters

- **PrivateKey**: Private key to use for signing the data. Expected size is 32 bytes.
- **PrivateKeyLength**: Size of the private key. Expected size is 32 bytes for Ed25519.
- **Data**: Buffer containing data to be signed.
- **DataLength**: Size of the buffer to be signed. Maximum size is 65536 bytes.
- **Signature [OUT]**: Buffer to store the signature to. Expected size is 64 bytes.
- **SignatureLength [IN/OUT]**: Size of the buffer to store the signature into. Expected size is 64 bytes. Will be updated with the number of bytes written to the buffer.

## Return Values

- **1**: Success  
  A Value of 1 means that the action was successful.
- **\<= 0**: Error  
  A value less than or equal to 0 means error.

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

[SecurityLocalVerifyEd25519](CAPLfunctionSecurityLocalVerifyEd25519.md)
