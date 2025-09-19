# C2xSecPacketGetSignerHashedId8

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecPacketGetSignerHashedId8( long packetHandle, byte signerHashedId8[] );
```

## Description

Gets the HashedId8 digest of the certificate which was used to sign the packet.

## Parameters

- **packetHandle**: Handle of the packet.
- **signerHashedId8**: Buffer in which the digest is copied, size must be 8 byte.

## Return Values

- **Any number**: Number of bytes copied.
- **8**: Success
- **0**: Failure

## Example

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long rxPacketHandle )
{
  byte hashedId8[8];
  C2xSecPacketGetHashedId8(rxPacketHandle, hashedId8);
}
```
