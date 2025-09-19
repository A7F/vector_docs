[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Security/Functions/CAPLfunctionX509ObjectFactory_copyX509DNAttribute.md)

**CAPL Functions** » [Security](../CAPLFunctionsSecurityOverview.md) » X509ObjectFactory_copyX509DNAttribute

# X509ObjectFactory_copyX509DNAttribute

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Method Syntax

`dword X509ObjectFactory_copyX509DNAttribute(qword objectHandle, qword& outHandleDNAttribute, qword toBeCopiedHandle)`

## Description

Creation function for deep copy of handle with type X509DNAttribute.

## Parameters

- **objectHandle**: (in) Handle with type 'X509ObjectFactory'. The function will be called in context of this handle.

## Selectors

—

## Return Values

- **1**: NoError: Operation was completed successfully.
- **-2**: Nullpointer: Error, the return value of the function was "NULL". The value is not available and the output buffer is unchanged.
- **-3**: BufferTooSmall: Error, the output buffer is too small. No value has been written.
- **-4**: InvalidHandle: Error, the provided objectHandle is invalid or not suitable for this function.
- **-5**: InvalidArgument: Error, one or more arguments are invalid for this function.
- **-6**: InvalidArgumentHandle: Error, one or more argument handles are invalid or not suitable for this function.

## Example

```plaintext
variables
{
  qword objectFactory;
  // Object handles
  qword pkiAccess, decoder, encoder, verifier, signer, rootCert, ecuCert, subject;
  // Result of certificate chain verification
  dword verificationResult;

  // Buffers
  byte keyBuffer[1000];
  byte byteBuffer[1000];
  char strBuffer[1000];
  dword keyBufferLen;
  dword byteBufferLen;
  dword strBufferLen;
}

void X509_Modify_Sign_And_Verify() {

  // X509 Object factory is the entry point for X.509 features. It is used to create object handles
  objectFactory = GetX509ObjectFactory();
  // Create handles for PkiAccess, Decoder, Encoder, Verifier
  X509ObjectFactory_createX509Decoder(objectFactory, decoder);
  X509ObjectFactory_createX509Encoder(objectFactory, encoder);
  X509ObjectFactory_createX509Verifier(objectFactory, verifier);
  X509ObjectFactory_createX509PkiAccess(objectFactory, pkiAccess);

  // Note: This sample code does not contain the required crypto material.
  // The required format is DER encoded X.509 certificate / private key as hexadecimal string, e.g. 112233AABBDD
  // Please use your existing (hex encoded) key and certificates or use an example value included in Security Manager Configurator

  // Decode the binary root certificate, lead certificate and root private key.
  keyBufferLen = 1000;
  X509ObjectFactory_BytesFromHexString(objectFactory, " *** YOUR HEX ENCODED SIGNER PRIVATE KEY *** ", keyBuffer, keyBufferLen);

  byteBufferLen = 1000;
  X509ObjectFactory_BytesFromHexString(objectFactory, " *** YOUR HEX ENCODED ECU CERTIFICATE *** ", byteBuffer, byteBufferLen);
  X509Decoder_DecodeCertificate(decoder, ecuCert, byteBuffer, byteBufferLen);

  byteBufferLen = 1000;
  X509ObjectFactory_BytesFromHexString(objectFactory, " *** YOUR HEX ENCODED SIGNER CERTIFICATE *** ", byteBuffer, byteBufferLen);
  X509PkiAccess_CreateSigner(pkiAccess, keyBuffer, keyBufferLen, byteBuffer, byteBufferLen, "SHA-256", signer);

  // Load the signer certificate handle
  X509Signer_GetSignerCertificate(signer, rootCert);

  // Now add the root certificates to the truststore of the verifier. These will be used for chain verification
  X509Verifier_AddTrustedCertificate(verifier, rootCert);

  // Verify the certificate against the truststore -> It is unchanged and must be valid
  verificationResult = 0;
  X509Verifier_VerifyCertificateChain(verifier, ecuCert, verificationResult);
  write("Verification result: %d", verificationResult);

  // Update the root certificates validity dates
  X509Certificate_SetValidFrom(rootCert, "20000101000000Z");
  X509Certificate_SetValidTo(rootCert, "20300101000000Z");
  X509Signer_UpdateAndSignCertificate(signer, rootCert);

  // Verify the certificate against the truststore -> Root certificate is re-signed and must be valid
  verificationResult = 0;
  X509Verifier_VerifyCertificateChain(verifier, ecuCert, verificationResult);
  write("Verification result: %d", verificationResult);

  // Get the subject DN from the certificate
  X509Certificate_GetSubjectDN(ecuCert, subject);

  // Update the ecu certificates validity dates
  X509Certificate_SetValidFrom(ecuCert, "20000101000000Z");
  X509Certificate_SetValidTo(ecuCert, "20300101000000Z");
  X509DN_SetValueForAttribute(subject, "2.5.4.3", "TESTTEST"); // Update CN
  X509DN_SetValueForAttribute(subject, "1.2.3.4", "ANOTHER_TESTTEST"); // Add custom Attribute

  // Now update the signature and all relevant fields (Issuer, Auth Key Identifier, SignatureAlgorithm)
  X509Signer_UpdateAndSignCertificate(signer, ecuCert);

  // Again verify the certificate against the truststore -> It received a fresh signature and must be invalid
  verificationResult = 0;
  X509Verifier_VerifyCertificateChain(verifier, ecuCert, verificationResult);
  write("Verification result: %d", verificationResult);

  // Utility to print the byte buffer into a hex string for printing
  write("Generated certificates:");
  write("Root:");
  byteBufferLen = 1000;
  X509Encoder_EncodeCertificate(encoder, rootCert, byteBuffer, byteBufferLen); // (DER-) encode the certificate structure into a byte buffer
  strBufferLen = 1000;
  X509ObjectFactory_BytesToHexString(objectFactory, byteBuffer, byteBufferLen, strBuffer, strBufferLen);
  write("Hex:\n%s", strBuffer);
  strBufferLen = 1000;
  X509Certificate_ToString(rootCert, strBuffer, strBufferLen);
  write("Textual:\n%s", strBuffer);
  write("Child:");
  byteBufferLen = 1000;
  X509Encoder_EncodeCertificate(encoder, ecuCert, byteBuffer, byteBufferLen); // (DER-) encode the certificate structure into a byte buffer
  strBufferLen = 1000;
  X509ObjectFactory_BytesToHexString(objectFactory, byteBuffer, byteBufferLen, strBuffer, strBufferLen);
  write("Hex:\n%s", strBuffer);
  strBufferLen = 1000;
  X509Certificate_ToString(ecuCert, strBuffer, strBufferLen);
  write("Textual:\n%s", strBuffer);
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
