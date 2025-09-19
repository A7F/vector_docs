# C2xGetTokenBitString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenBitString.md)

**CAPL Functions** » **Car2x** » **C2xGetTokenBitString**

## Function Syntax

```plaintext
long C2xGetTokenBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bufferSize, byte buffer[]); // form 1
long C2xGetTokenBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bufferSize, char buffer[]); // form 2
```

## Description

This function gets the bit string value of a token.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **userDefinedPayload**
- **tokenDesignator**: Name of the token, e.g. **bitString**
- **bufferSize**: Size of the buffer in bits
- **buffer**: Buffer in which the data is copied

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
byte brakePedalActive(long channel, longdir, longradioChannel, long signalStrength, long sigQuality, long packet)
{
  byte accelerationControl[1];

  if (C2xGetTokenBitString(packet, "CAM", "cam.camParameters.highFrequencyContainer.basicVehicleContainerHighFrequency.accelerationControl", 7, accelerationControl))
  {
    return accelerationControl[0] & 0x80;
  }
  return 0;
}
```

