[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecCertificateCreate.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecCertificateCreate

# C2xSecCertificateCreate

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecCertificateCreate(long originalCertificateHandle, dword validityInSeconds);
long C2xSecCertificateCreate(long originalCertificateHandle, dword validityInSeconds, long signerCertificateHandle);
```

## Description

Generate a new certificate based on another certificate. The certificate is only valid while the measurement is running and it is automatically discarded afterwards. The certificate is only known to the [realtime part](../../../CANoeCANalyzer/CANoeCANalyzerConcept.md#Real-Time) of your CANoe DE product. The [analysis area](../../../CANoeCANalyzer/CANoeCANalyzerConcept.md#Analysis) only gets knowledge of it when it is transmitted in a message.

## Parameters

- **originalCertificateHandle**: Handle of a certificate which is used as a template. The new certificate inherits all properties of the original certificate except the key pair and those properties specified by the other parameters below.
- **validityInSeconds**: The new certificate is at least valid for the specified seconds past the current CANoe DE product simulation time. The validity period of the new certificate starts at midnight of the current simulation day.
- **signerCertificateHandle**: Handle to a certificate to be used as certificate signer. If this parameter is omitted, the original certificate’s signer is used. If the original certificate is a Root (self signed) certificate this parameter has no meaning. To use a certificate as signer the matching private key must be known and the signer certificate’s protocol version must match that of the one to be signed.

## Return Values

- **0**: Failure
- **≠0**: Handle of the new certificate

## Example

```plaintext
long itsCertHdl;
long pcaCertHdl;
long newPcaCertHdl;
long newItsCertHdl;

itsCertHdl = C2xSecCertificateGetHandle("its"); // get original its certificate
pcaCertHdl = C2xSecCertificateGetHandle("pca"); // get original pca certificate

// create new pca certificate based on the original pca certificate
// validity is at least 24 hours from current simulation time
// share the same root with the original pca
newPcaCertHdl = C2xSecCertificateCreate(pcaCertHdl, 60*60*24);

// create new its certificate based on the original its certificate
// validity is at least 1 hour from current simulation time
// use the new pca certificate as signer of the new its certificate
newItsCertHdl = C2xSecCertificateCreate(itsCertHdl, 60*60, newPcaCertHdl);
```

[See Also](javascript:void(0);)