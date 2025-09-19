# C2xSetTokenBitOfBitString

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSetTokenBitOfBitString( long packet, char protocolDesignator[], char tokenDesignator[], char namedBit[], long value ); // form 1
long C2xSetTokenBitOfBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bitPosition, long value ); // form 2
```

## Description

This function sets a bit of a bit string that is specified either by its name (form 1) or by its position (form 2) to a new value.

If the bit string does not yet contain the specified bit, the bit string is resized up to the specified bit. On resizing, the new bits before the specified bit are set to 0.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**.
- **tokenDesignator**: Name of the token, e.g. **data**.
- **namedBit**: Name of the bit.
- **bitPosition**: Zero based index of the bit.
- **value**: New value of the bit.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle;
long result;

packetHandle = C2xInitPacket("userDefinedPayload");
if ((result = C2xSetTokenBitOfBitString(packetHandle, "userDefinedPayload","bitString", "secondBitsName", 1)) == 0)
{
  //bit string "bitString" now has the value "01"
}
else if (result == 460103)
{
  //Invalid Argument – in this case this most probably means
  //that the passed bit name "secondBitsName" is unknown
}
else
{
  //other error
}
```
