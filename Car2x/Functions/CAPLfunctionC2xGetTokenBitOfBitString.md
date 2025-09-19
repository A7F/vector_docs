# C2xGetTokenBitOfBitString

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xGetTokenBitOfBitString.md)

**CAPL Functions** » **Car2x** » **C2xGetTokenBitOfBitString**

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long C2xGetTokenBitOfBitString( long packet, char protocolDesignator[], char tokenDesignator[], char namedBit[] ); // form 1
long C2xGetTokenBitOfBitString( long packet, char protocolDesignator[], char tokenDesignator[], long bitPosition ); // form 2
```

## Description

This function gets the value of a bit in a bit string that is specified either by its name (form 1) or by its position (form 2).

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**
- **tokenDesignator**: Name of the token, e.g. **data**
- **namedBit**: Name of the bit
- **bitPosition**: Zero based index of the bit

## Return Values

Value of the bit.

## Example

See example of [C2xSetTokenBitOfBitString](CAPLfunctionC2xSetTokenBitOfBitString.md).

