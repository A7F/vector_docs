[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSecPacketIsSecured.md)

**CAPL Functions** » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xSecPacketIsSecured

# C2xSecPacketIsSecured

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSecPacketIsSecured (long packetHandle);
```

## Description

Checks if the packet is secured by a security layer ([Security Header](../../../CANoeCANalyzer/Car2x/protocols/geoNetworking302/protocolGeoNetworkingSH.md) or [WAVE Security Services](../../../CANoeCANalyzer/Car2x/protocols/wave/protocolWaveSecurityServices.md)).

## Parameters

- **packetHandle**: Handle of the packet.

## Return Values

- **1**: The packet is secured.
- **0**: The packet is not secured.

## Example

```plaintext
void OnC2xPacket (long channel, long dir, long radioChannel, long signalStrength, long sigQuality, long packet)
{
  byte hashedId8[8] ;

  if (C2xSecPacketIsSecured(packet))
  {
    C2xSecPacketGetSignerHashedId8(packet, hashedId8);
    /* ... */
  }
}
```

[See Also](javascript:void(0);)