# C2xIsTokenAvailable

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xIsTokenAvailable( long packet, char protocolDesignator[], char tokenDesignator[] );
```

## Description

This function checks if the specified token is part of the packet.

**Note:** For ASN.1 based protocols, tokens that are not set are not part of the packet between the functions calls of [C2xInitPacket](CAPLfunctionC2xInitPacket.md) and [C2xCompletePacket](CAPLfunctionC2xCompletePacket.md). For other protocols, the non-optional tokens are always part of the packet.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md).
- **tokenDesignator**: Name of the token.

## Return Values

- **1**: Token is part of the packet.
- **0**: Token is not part of the packet.

## Example

```plaintext
long packet;

//create geoNetworking unicast
packet = C2xInitPacket("geoNetworking");

//spvNetAddr is optional but headertype (ht) is unicast per default which contains spvNetAddr
if (!C2xIsTokenAvailable(packet, "geoNetworking","spvNetAddr"))
{
  write("error! spvNetAddr is not available in geoNetworking unicast");
}

//transform packet to geoNetworking broadcast
if (C2xSetTokenInt(packet, "geo_cnh", "ht", 4) != 0)
{
  write("error! C2xSetTokenInt failed");
}
if (C2xResizeToken(packet, "geoNetworking", "header", 384) != 0)
{
  write("error! C2xResizeToken failed");
}

//broadcast does not contain spvNetAddr
if (C2xIsTokenAvailable(packet, "geoNetworking", "spvNetAddr"))
{
  write("error! spvNetAddr is available in geoNetworking broadcast");
}
```

