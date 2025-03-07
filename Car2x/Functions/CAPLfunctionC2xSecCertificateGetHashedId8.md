[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecCertificateGetHashedId8.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecCertificateGetHashedId8

# C2xSecCertificateGetHashedId8

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

```plaintext
long C2xSecCertificateGetHashedId8( long certificateHandle, byte hashedId8[] );
```

## Description

Gets HashedId8 digest of a certificate.

## Parameters

- **certificateHandle**: Handle of the certificate
- **hashedId8**: Buffer in which the digest is copied, size must be 8 bytes. In some protocols this parameter is called certId8.

## Return Values

- **Any number**: Number of bytes copied.
- **8**: Success
- **0**: Failure

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long rxPacketHandle )
{
  long certificateHandle;
  byte hashedId8[8];
  certificateHandle = C2xSecPacketGetSignerHandle(rxPacketHandle);
  C2xSecCertificateGetHashedId8(certificateHandle, hashedId8);
}
```

[See Also](javascript:void(0);)