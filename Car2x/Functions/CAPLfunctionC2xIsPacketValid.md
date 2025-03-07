# C2xIsPacketValid

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xIsPacketValid.md)

**CAPL Functions** » **Car2x** » **C2xIsPacketValid**

## Function Syntax

```plaintext
long C2xIsPacketValid( long packet );
```

## Description

This function checks if a received packet has a protocol error. Packets with a protocol error are marked with an error icon in the Trace Window.

## Parameters

- **packet**: Handle of a packet that should be checked.

## Return Values

- **0**: Packet is valid.
- **!0**: Packet has protocol errors.

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  C2xReceivePacket( "OnC2xPacket");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  if (C2xIsPacketValid( packet ) != 0)
  {
    write( "Receive packet with protocol error" );
  }
}
```

[See Also](javascript:void(0);)