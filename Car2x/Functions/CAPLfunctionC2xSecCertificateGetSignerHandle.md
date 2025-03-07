# C2xSecCertificateGetSignerHandle

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecCertificateGetSignerHandle

**Valid for:** CANoe DE

## Function Syntax

```plaintext
long C2xSecCertificateGetSignerHandle( long certificateHandle );
```

## Description

Gets the signer (parent) certificate of a certificate.

## Parameters

- **certificateHandle**: Handle of the certificate

## Return Values

- **0**: —
- **≠0**: Handle of the signer (parent) certificate

## Example

```plaintext
long certificateHandle;
long signerHandle;
certificateHandle = C2xSecCertificateGetHandle( "MyCert" );
if (certificateHandle != 0)
{
  signerHandle = C2xSecCertificateGetSignerHandle(certificateHandle);
}
```

## See Also

- [OnC2xPacket](../Callbacks/CAPLfunctionC2xOnC2xPacket.md#aanchor23975)
- [C2xAddToken](CAPLfunctionC2xAddToken.md#aanchor432)
- [C2xSecCertificateGetHandle](CAPLfunctionC2xSecCertificateGetHandle.md#aanchor20814)
- [C2xSecCertificateGetSignerHashedId8](CAPLfunctionC2xSecCertificateGetSignerHashedId8.md#aanchor29936)
- [C2xSecPacketGetSignerHandle](CAPLfunctionC2xSecPacketGetSignerHandle.md#aanchor21036)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)