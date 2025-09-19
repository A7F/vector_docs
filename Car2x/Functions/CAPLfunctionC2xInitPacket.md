# C2xInitPacket

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xInitPacket.md)

**CAPL Functions** » **Car2x** » **C2xInitPacket**

## Function Syntax

- `long C2xInitPacket( void );`
- `long C2xInitPacket( char protocolDesignator[] );`
- `long C2xInitPacket( char protocolDesignator[], char packetTypeDesignator[] );`
- `long C2xInitPacket( long packetToCopy );`
- `long C2xInitPacket( long rawDataLength, byte rawData[] );`
- `long C2xInitPacket( long rawDataLength, char rawData[] );`
- `long C2xInitPacket( long rawDataLength, struct * rawDataStruct );`

## Description

This function creates a new WLAN packet. Other functions can access the newly created packet with the returned handle. Protocol fields that are marked as **InitProtocol** in the protocol description are initialized.

## Parameters

- **protocolDesignator**: Designator of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), which should be used for initialization.
- **packetTypeDesignator**: [Designator](../../../CANoeCANalyzer/Car2x/asn1/asnUsePacketTypeDesignators.md) of the packet type.
- **packetToCopy**: Handle of a packet created with **C2xInitPacket** before or handle of a packet received within a callback ([OnC2xPacket](../Callbacks/CAPLfunctionC2xOnC2xPacket.md)). The header and the data of this packet are copied to the newly created packet.
- **rawDataLength**: Length of **rawData** in bytes.
- **rawData/rawDataStruct**: Raw data of a WLAN packet that is used to initialize the new packet.

## Return Values

With [C2xGetLastError](CAPLfunctionC2xGetLastError.md), you can check if the function has been processed successfully.

- **0**: —
- **≠0**: Handle of the created packet.

## Example

```plaintext
long packetHandle;
char error[100];
byte macAddress[6] = { 0x20, 0x00, 0x00, 0x00, 0x00, 0x01 };

// create packet
packetHandle = C2xInitPacket("geo_cnh");
if (C2xGetLastError() == 0)
{
  // set protocol fields
  C2xSetTokenData(packetHandle, "wlan", "address2", 6, macAddress);
  C2xSetTokenData(packetHandle, "eth", "source", 6, macAddress);

  // set CNH values
  C2xSetTokenInt(packetHandle, "geo_cnh", "lpvSpeed", 100);
  C2xSetTokenInt(packetHandle, "geo_cnh", "lpvHeading", 1800);
  C2xSetTokenInt(packetHandle, "geo_cnh", "lpvAltitude", 0);

  // Complete and send packet
  C2xCompletePacket(packetHandle);
  C2xOutputPacket(packetHandle);

  // release packet
  C2xReleasePacket(packetHandle);
}
else
{
  C2xGetLastErrorText(elCount(error), error);
  write("Error: %s", error);
}
```

**See Also**: [C2xGetLastError](CAPLfunctionC2xGetLastError.md)

---
