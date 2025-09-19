# C2xGetTokenString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenString.md)

**CAPL Functions** » **Car2x** » **C2xGetTokenString**

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xGetTokenString( long packet, char protocolDesignator[], char tokenDesignator[], long bufferSize, char buffer[] );
```

## Description

This function copies characters from the token and adds a terminating `\0`.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**
- **tokenDesignator**: Name of the token, e.g. **data**
- **bufferSize**: Size of buffer in byte. This function adds a terminating `\0`. Thus the maximum number of copied characters is **bufferSize**-1.
- **buffer**: Buffer in which the data are copied

## Return Values

With [C2xGetLastError](CAPLfunctionC2xGetLastError.md) you can check if the function has been processed successfully.

- **0**: —
- **≠0**: Number of copied characters

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  C2xReceivePacket("OnC2xPacket");
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  char rx_str[100];
  char error[100];

  // get the payload of the packet
  C2xGetTokenString( packet, "geo_cnh", "data", elCount(rx_str), rx_str );

  if (C2xGetLastError() == 0)
  {
    write(rx_str);
  }
  else
  {
    C2xGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```
