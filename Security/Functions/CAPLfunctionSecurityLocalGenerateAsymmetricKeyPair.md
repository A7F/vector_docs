# SecurityLocalGenerateAsymmetricKeyPair

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

`SecurityLocalGenerateAsymmetricKeyPair(dword keyPairType, byte[] privateKey, dword& privateKeyLength, byte[] publicKey, dword& publicKeyLength)`

## Description

Generates key pair (public and private key) for the specified algorithm. Uses internally seeded random number generator.

Currently supported algorithms: Ed25519 (public key: 32 bytes, private key: 32 bytes)

## Parameters

- **keyPairType**  
  Type of keys to be generated. Available types:  
  Ed25519 = 1

- **privateKey**  
  OUT parameter  
  Buffer to write the generated private key to. Expected size depends on the key type.

- **privateKeyLength**  
  IN/OUT parameter  
  Expects the size of the provided private key buffer.  
  Is updated with the bytes written into the buffer.

- **publicKey**  
  OUT parameter  
  Buffer to write the generated private key to. Expected size depends on the key type.

- **publicKeyLength**  
  IN/OUT parameter  
  Expects the size of the provided private key buffer.  
  Is updated with the bytes written into the buffer.

## Return Values

- **1**  
  Success  
  A Value of 1 means that the action was successful.

- **\<= 0**  
  Error  
  A value less than or equal to 0 means error.

## Example

**Note**  

```plaintext
byte priv[1000];
byte pub[1000];
dword privSize;
dword pubSize;
privSize = elcount(priv);
pubSize = elcount(pub);
SecurityLocalGenerateAsymmetricKeyPair(1, priv, privSize, pub, pubSize);
```

[SecurityLocalVerifyEd25519](CAPLfunctionSecurityLocalVerifyEd25519.md) • [SecurityLocalSignEd25519](CAPLfunctionSecurityLocalSignEd25519.md)
