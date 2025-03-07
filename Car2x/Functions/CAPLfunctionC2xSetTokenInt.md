[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetTokenInt.md)

**CAPL Functions** » **Car2x** » **C2xSetTokenInt**

# C2xSetTokenInt

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSetTokenInt( long packet, char protocolDesignatorl[], char tokenDesignator[], long value ); // form 1
long C2xSetTokenInt( long packet, char protocolDesignatorl[], char tokenDesignator[], long byteOffset, long length, long networkByteOrder, long value ); // form 2
```

## Description

This function sets the integer value of a token. Form 2 with byte offset sets a part of the token data as integer.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**.
- **tokenDesignator**: Name of the token, e.g. **lpvSpeed**.
- **byteOffset**: Offset from the beginning of the token in byte.
- **length**: Length of the integer value, must be 1, 2, 3 or 4 byte.
- **networkByteOrder**:
  - 0: INTEL (little-endian)
  - 1: MOTOROLA (big-endian)
- **value**: New integer value.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

See example of [C2xInitPacket](CAPLfunctionC2xInitPacket.md).

[See Also](javascript:void(0);)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)