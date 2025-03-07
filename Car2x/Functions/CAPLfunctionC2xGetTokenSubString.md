[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenSubString.md)

[CAPL Functions](../../CAPLfunctions.md) » [Car2x](../CAPLfunctionsCar2xOverview.md) » C2xGetTokenSubString

# C2xGetTokenSubString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xGetTokenSubString( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, char buffer[] );
```

## Description

This function copies a specified number of characters from a given position inside the token and adds a terminating `\0`.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**
- **tokenDesignator**: Name of the token, e.g. **data**
- **byteOffset**: Offset from the beginning of the token in byte
- **length**: Number of characters to be copied
- **buffer**: Buffer in which the characters are copied. This function adds a terminating `\0`. Thus, the size of the buffer must be at least one byte larger than **length**.

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
  C2xGetTokenSubString( packet, "geo_cnh", "data", 8, elCount(rx_str), rx_str );
  // would access payload of a cnh packet

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

[See Also](javascript:void(0);)