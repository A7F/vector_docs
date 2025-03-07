[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecCertificateGetStatus.md)

**CAPL Functions** » **Car2x** » **C2xSecCertificateGetStatus**

# C2xSecCertificateGetStatus

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSecCertificateGetStatus( long certificateHandle );
```

## Description

Gets validity status of a certificate.

## Parameters

- **certificateHandle**: Handle of the certificate

## Return Values

The validity status consists of 3 bit fields which are combined using a binary OR operation.

**The overall status is masked with 0xf000 and has the meaning:**

- **0x0000**: Internal error.
- **0x1000**: At least one signer in trust chain is unknown.
- **0x2000**: At least one signature in trust chain is invalid.
- **0x3000**: All signatures in the chain are valid and end in a certificate which is marked as trusted in the [Certificate Manager](../../../CANoeCANalyzer/Ribbon/File/Options/BussystemsProtocols/BussystemsProtocolsCar2x.md#Car2xCertificateManager).

**The relevant subject in the trust chain is identified by the mask 0x0f00:**

- **0x0100**: Root CA certificate
- **0x0200**: Pseudonym CA certificate
- **0x0300**: Longterm CA certificate
- **0x0400**: Pseudonym certificate
- **0x0500**: Longterm certificate
- **0x0600**: Certificate Revocation List certificate
- **0x0700**: Message

**In case of an invalid status the reason is specified by the mask 0x000f:**

- **0x0001**: Invalid signature.
- **0x0002**: Wrong certificate type.
- **0x0003**: Root known but not trusted.
- **0x0004**: CANoe simulation time not in permitted period.

**Status examples:**

- 0x1400 means the status is unknown, because the Pseudonym certificate signer is unknown
- 0x2702 means the status is invalid, because the message signer is not a Pseudonym certificate
- 0x3100 means the status is valid, because the Root CA certificate is trusted

## Example

```plaintext
long certificateHandle;
certificateHandle = C2xSecCertificateGetHandle( "MyCert" );
switch (C2xSecCertificateGetStatus(certificateHandle) & 0xF000)
{
  case 0x1000: // unknown
    break;
  case 0x2000: // invalid
    break;
  case 0x3000: // valid
    break;
}
```

[See Also](javascript:void(0);)