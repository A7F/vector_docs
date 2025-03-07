[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xDispatchPacket.md)

[CAPL Functions](../../CAPLfunctions.md) » Car2x » C2xDispatchPacket

# C2xDispatchPacket

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xDispatchPacket( long packet,  dword direction );
```

## Description

This function dispatches a packet to CANoe DE product application (analyze), it isn’t given to the hardware driver. The direction (Rx, Tx TxRq) that is displayed e.g. in the Trace Window can be defined.

## Parameters

- **packet**: Handle of a packet that has been initialized and completed (see example).
- **direction**:
  - 0 = Rx
  - 1 = Tx
  - 2 = TxRq

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle;
char error[100];
byte macAddress[6] = { 0x20, 0x00, 0x00, 0x00, 0x00, 0x01 };

// create packet
packetHandle = C2xInitPacket("geo_eh");
if (C2xGetLastError() == 0)
{
  // Set protocol fields
  C2xSetTokenData( packetHandle, "wlan", "address2", 6, macAddress );
  C2xSetTokenData( packetHandle, "eth",  "source",   6, macAddress );

  // set EH values
  C2xSetTokenInt( packetHandle, "geo_eh", "lpvSpeed",    100 );
  C2xSetTokenInt( packetHandle, "geo_eh", "lpvHeading",  1800 );
  C2xSetTokenInt( packetHandle, "geo_eh", "lpvAltitude", 0 );

  // Complete and send packet
  C2xCompletePacket( packetHandle );

  // Dispatch the packet in tx direction
  C2xDispatchPacket( packetHandle, 1);

  // Release packet
  C2xReleasePacket( packetHandle );
}
else
{
  C2xGetLastErrorText( elCount(error), error );
  write("Error: %s", error );
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)