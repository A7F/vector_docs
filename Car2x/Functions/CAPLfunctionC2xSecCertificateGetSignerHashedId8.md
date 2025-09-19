# C2xSecCertificateGetSignerHashedId8

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecCertificateGetSignerHashedId8( long certificateHandle, byte signerHashedId8[] );
```

## Description

Gets the signer (parent) certificate’s HashedId8 digest. In some protocols the digest is called CertId8.

## Parameters

- **certificateHandle**: Handle of the certificate.
- **signerHashedId8**: Buffer in which the digest is copied, size must be 8 byte.

## Return Values

- **Any number**: Number of bytes copied.
- **8**: Success
- **0**: Failure

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long rxPacketHandle )
{
  long certificateHandle;
  byte signerHashedId8[8];
  certificateHandle = C2xSecPacketGetSignerHandle( rxPacketHandle );
  if (certificateHandle != 0)
  {
    C2xSecCertificateGetSignerHashedId8(certificateHandle, signerHashedId8);
  }
}
```
