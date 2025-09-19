# C2xSecPacketSetSignerType

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecPacketSetSignerType

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xSecPacketSetSignerType(long packetHandle, long signerType);
```

## Description

Specifies how the message signer information is included in the message. It is possible to add only a digest (HashedId8), to transmit the signer’s certificate or to transmit the complete certificate chain.

## Parameters

- **packetHandle**: Handle of the packet
- **signerType**: Signer information type
  - 0: unsecured
  - 1: digest
  - 2: certificate
  - 3: certificate chain

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle;
long certificateHandle;
packetHandle = C2xInitPacket("geo_eh", "BEACON | SH");
certificateHandle = C2xSecCertificateGetHandle("MyCert");
C2xSecPacketSetSignerHandle(packetHandle, certificateHandle);
C2xSecPacketSetSignerType(packetHandle, 2); // send certificate
C2xCompletePacket(packetHandle);
C2xOutputPacket(packetHandle);
```
