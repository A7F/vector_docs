# C2xSecPacketGetStatus

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecPacketGetStatus( long packetHandle );
```

## Description

Gets validity status of a packet. This is interesting for received packets only and indicates if the signature of the security header of the packet is valid. In case the signature is not valid, an appropriate error code is returned.

## Parameters

- **packetHandle**: Handle of the packet.

## Return Values

The validity status consists of 3 bit fields which are combined using a binary OR operation.

**The overall status is masked with 0xf000 and has the meaning:**

- `0x0000`: Internal error.
- `0x1000`: At least one signer in trust chain is unknown.
- `0x2000`: At least one signature in trust chain is invalid.
- `0x3000`: All signatures in the chain are valid and end in a certificate which is marked as trusted in the [Certificate Manager](../../../CANoeCANalyzer/Ribbon/File/Options/BussystemsProtocols/BussystemsProtocolsCar2x.md#Car2xCertificateManager).

**The relevant subject in the trust chain is identified by the mask 0x0f00:**

- `0x0100`: Root CA certificate
- `0x0200`: Pseudonym CA certificate
- `0x0300`: Longterm CA certificate
- `0x0400`: Pseudonym certificate
- `0x0500`: Longterm certificate
- `0x0600`: Certificate Revocation List certificate
- `0x0700`: Message

**In case of an invalid status the reason is specified by the mask 0x000f:**

- `0x0001`: Invalid signature.
- `0x0002`: Wrong certificate type.
- `0x0003`: Root known but not trusted.
- `0x0004`: CANoe simulation time not in permitted period.

**Status examples:**

- `0x1400` means the status is unknown, because the Pseudonym certificate signer is unknown
- `0x2702` means the status is invalid, because the message signer is not a Pseudonym certificate
- `0x3100` means the status is valid, because the Root CA certificate is trusted

## Example

```plaintext
variables
{
  byte hashedId8[8];
}

void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long rxPacketHandle )
{
  long rxCertificateHandle;
  switch (C2xSecPacketGetStatus(rxPacketHandle) & 0xF000)
  {
    case 0x0000: break; // no SH included or other error
    case 0x1000:            // unknown
    {
      // get the certificate digest
      C2xGetTokenData(rxPacketHandle, "geo_sh", "signerHashedId", elCount(hashedId8), hashedId8);
      break;
    }
    case 0x2000: // invalid
    {
      // check used certificate
      break;
    }
    case 0x3000: break; // valid
  }
}
```
