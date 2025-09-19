# C2xGetTokenData

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long length, char buffer[] );`
- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignatorl[], long length, byte buffer[] );`
- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long length, struct bufferStruct );`
- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, char buffer[] );`
- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, byte buffer[] );`
- `long C2xGetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, struct bufferStruct );`

## Description

This function requests the data or a part of data of a token.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**
- **tokenDesignator**: Name of the token, e.g. **data**
- **byteOffset**: Offset from the beginning of the token in byte
- **length**: Number of bytes to be copied. Make sure size of destination (**buffer** or **bufferStruct**) is equal or larger than length.
- **buffer**: Buffer in which the data are copied
- **bufferStruct**: Struct in which the data are copied

## Return Values

With [C2xGetLastError](CAPLfunctionC2xGetLastError.md) you can check if the function has been processed successfully.

- **0**: —
- **≠0**: Number of copied bytes

## Example

Node **System - PreStart** in CAPL Browser

```plaintext
on preStart
{
  C2xReceivePacket( "OnC2xPacket" );
}
```

Node **Callback Function** in CAPL Browser

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  byte data[5];
  char error[100];

  // get payload of the receive packet
  C2xGetTokenData( packet, "geo_cnh", "data", 5, data );
  if (C2xGetLastError() == 0)
  {
    // do something with data
  }
  else
  {
    C2xGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```
