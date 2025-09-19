# C2xSetTokenBitString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
long C2xSetTokenBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bufferSize, byte buffer[] ); // form 1
long C2xSetTokenBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bufferSize, char buffer[] ); // form 2
```

## Description

This function sets the bit string of a token.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **userDefinedPayload**.
- **tokenDesignator**: Name of the token, e.g. **bitString**.
- **bufferSize**: Size of buffer in bits.
- **buffer**: Buffer in which the data is copied.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
void accelCtrl(long packet, byte value)
{
  byte accelerationControl[1];
  accelerationControl[0] = value;

  C2xSetTokenBitString(packet, "CAM", "cam.camParameters.highFrequencyContainer.basicVehicleContainerHighFrequency.accelerationControl", 7, accelerationControl);
}
```
