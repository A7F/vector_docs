# C2xSetTokenData

[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetTokenData.md)

**CAPL Functions** » **Car2x** » **C2xSetTokenData**

**Valid for**: CANoe DE

## Function Syntax

- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long length, char data[] );`
- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long length, byte data[] );`
- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long length, struct dataStruct );`
- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, char data[] );`
- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, byte data[] );`
- `long C2xSetTokenData( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, long length, struct dataStruct );`

## Description

This function sets the data or a part of data of a token. It does not resize the token. Use [C2xResizeToken](CAPLfunctionC2xResizeToken.md) to change the length.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **eth**.
- **tokenDesignator**: Name of the token, e.g. **source**.
- **byteOffset**: Offset from the beginning of the token in byte.
- **length**: Number of bytes to be copied.
- **data**: Data that are copied to the token.
- **dataStruct**: Struct containing the data.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

See example of [C2xInitPacket](CAPLfunctionC2xInitPacket.md).

**See Also**: [Various CAPL Functions](javascript:void(0);)

© Vector Informatik GmbH
- CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3
- [Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)
- [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)