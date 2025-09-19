# C2xSecPacketSetSignerHandle

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecPacketSetSignerHandle( long packetHandle, long certificateHandle );
```

## Description

Assigns a certificate to a Tx packet.

The assigned certificate is used to sign the Tx packet when [C2xCompletePacket(packetHandle)](CAPLfunctionC2xCompletePacket.md) is called.

The protocol type and version of the packet must match the protocol type and version of the certificate. E.g. an ETSI TS 103 097 encoded message cannot be signed using an IEEE 1609.2 encoded certificate.

## Parameters

- **packetHandle**: Handle of the packet.
- **certificateHandle**: Handle of the certificate.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle;
long certificateHandle;
packetHandle = C2xInitPacket("geo_eh", "BEACON | SH");
certificateHandle = C2xSecCertificateGetHandle ( "MyCert" );
C2xSecPacketSetSignerHandle(packetHandle, certificateHandle);
C2xCompletePacket(packetHandle);
C2xOutputPacket(packetHandle);
```

