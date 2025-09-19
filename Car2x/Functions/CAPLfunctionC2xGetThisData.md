# C2xGetThisData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function is only usable in a CAPL callback that had been registered with [C2xReceivePacket](CAPLfunctionC2xReceivePacket.md).

## Function Syntax

```plaintext
long C2xGetThisData( long offset, long bufferSize, byte buffer[] );
long C2xGetThisData( long offset, long bufferSize, char buffer[] );
long C2xGetThisData( long offset, long bufferSize, struct* buffer );
```

## Description

This function gets the payload data of the highest interpretable protocol.

## Parameters

- **offset**: Byte offset relative to the beginning of the payload
- **bufferSize**: Number of requested bytes
- **buffer**: Buffer in which the requested data are copied

## Return Values

Number of copied data bytes.

## Example

**Node System - PreStart in CAPL Browser**

```plaintext
on preStart
{
  C2xReceivePacket( "OnC2xPacket");
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  byte payload[8];
  long len;

  len = C2xGetThisData( 0, 8, payload);
  write( "Receive payload with %d bytes", len );
}
```

