# C2xResizeToken

**Valid for**: CANoe DE

### Note
This function can only be used with resizable tokens. These are e.g. the **header**, **data**, and all ASN.1 defined bit string tokens. If a token is not resizable the error code 46-0125 is returned.

## Function Syntax

```plaintext
long C2xResizeToken( long packet, char protocolDesignator[], char tokenDesignator[], long newBitLength );
```

## Description

This function sets the length of a token.

In case the token length is increased by full bytes, the additional bytes are initialized with 0.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md)
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **wlan**
- **tokenDesignator**: Name of the token, e.g. **data**
- **newBitLength**: New length of the token in bits

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

See example of [C2xInitPacket](CAPLfunctionC2xInitPacket.md)

