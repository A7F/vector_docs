[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenInt.md)

**CAPL Functions** » **Car2x** » **C2xGetTokenInt**

# C2xGetTokenInt

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xGetTokenInt( long packet, char protocolDesignator[], char tokenDesignator[] ); // form 1
long C2xGetTokenInt( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, long networkByteOrder ); // form 2
```

## Description

This function requests the integer value of a token. Form 2 with byte offset returns a part of the token data as integer.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**
- **tokenDesignator**: Name of the token, e.g. **lpvSpeed**
- **byteOffset**: Offset from the beginning of the token in byte
- **length**: Length of the integer value, must be 1, 2, 3 or 4 byte
- **networkByteOrder**:
  - 0: INTEL (little-endian)
  - 1: MOTOROLA (big-endian)

## Return Values

With [C2xGetLastError](CAPLfunctionC2xGetLastError.md) you can check if the function has been processed successfully.

- **0**: —
- **≠0**: Integer value of the token

## Example

**Node System - PreStart in CAPL Browser**

```plaintext
on preStart
{
  C2xReceivePacket( "OnC2xPacket" );
}
```

**Node Callback Function in CAPL Browser**

```plaintext
void OnC2xPacket( long channel, long dir, long radioChannel, long signalStrength, long signalQuality, long packet )
{
  long speed;
  char error[100];

  // get lpvSpeed of the receive packet
  speed = C2xGetTokenInt( packet, "geo_cnh", "lpvSpeed" );
  if (C2xGetLastError() == 0)
  {
    // do something with lpvSpeed
  }
  else
  {
    C2xGetLastErrorText( elCount(error), error );
    write("Error: %s", error );
  }
}
```

[See Also](javascript:void(0);)
```markdown