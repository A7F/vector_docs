# C2xSetTokenPhys

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`long C2xSetTokenPhys(long packet, char[] protocolDesignator, char[] tokenDesignator, double value)`

## Description

This function sets the physical value of the token in the packet. This function succeeds only if following requirements apply:

- The token path specified by the tokenDesignator parameter belongs to ASN.1 part of the message, setting the physical value for lower protocols like GeoNet or WSMP is not supported.
- The ASN.1 token specified by the tokenDesignator parameter has a raw/physical value conversion factor defined in the database (column "Format" in the Car2x Network Explorer must not be empty for this ASN.1 token).

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md) or was provided as callback function parameter.
- **protocolDesignator**: Name of the protocol, e.g. CAM.
- **tokenDesignator**: Name of the ASN.1 token, e.g. cam.camParameters.basicContainer.referencePosition.latitude.
- **value**: The physical value of the token.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```c
void OnPreTxDENM(LONG packet)
{
  C2xSetTokenPhys(packet, "DENM", "denm.management.eventPosition.latitude", 10.11);
  C2xSetTokenPhys(packet, "DENM", "denm.management.eventPosition.longitude", -2.2);
}
```
