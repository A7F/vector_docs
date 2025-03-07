[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Car2x/Functions/CAPLfunctionC2xSetTokenString.md)

**CAPL Functions** » **Car2x** » **C2xSetTokenString**

# C2xSetTokenString

[Valid for: CANoe DE](../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long C2xSetTokenString( long packet, char protocolDesignator[], char tokenDesignator[], char data[] );
long C2xSetTokenString( long packet, char protocolDesignator[], char tokenDesignator[], long byteOffset, char data[] );
```

## Description

This function copies the string value to the token without terminating `\0`.

## Parameters

- **packet**: Handle of a packet that has been created with [C2xInitPacket](CAPLfunctionC2xInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/Car2x/protocols/protocoloverviewCar2x.md), e.g. **geo_cnh**.
- **tokenDesignator**: Name of the token, e.g. **data**.
- **byteOffset**: Offset from the beginning of the token in byte.
- **data**: Data as string.

## Return Values

- **0**: Success
- **≠0**: [Error code](../CAPLfunctionsCar2xErrorCodes.md)

## Example

```plaintext
long packetHandle;

// create packet
packetHandle = C2xInitPacket( "geo_cnh" );

// set geo_cnh payload
C2xResizeToken( packetHandle, "geo_cnh", "data", 5*8 /*bits*/ );
C2xSetTokenString( packetHandle, "geo_cnh", "data", "Hello" );

// complete and send packet
C2xCompletePacket( packetHandle );
C2xOutputPacket( packetHandle );

// release packet
C2xReleasePacket( packetHandle );
```

[See Also](javascript:void(0);)