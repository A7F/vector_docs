# AfdxSetTokenString

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxSetTokenString( long packet, long protocolDesignator[], long tokenDesignator[], long offset, char data[] );
```

## Description

This function copies the string value to the token without terminating "\0".

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md), e.g. "afdx".
- **tokenDesignator**: Name of the token, e.g. "data".
- **offset**: This is the offset from the beginning of the token's data area. If this is 0, data is copied starting at byte 0 of the token's data area.
- **data**: Data as string.

## Return Values

- **0**:
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

```plaintext
long packetHandle;

// create packet
packetHandle = AfdxInitPacket( "afdx" );

// set afdx payload
AfdxResizeToken( packetHandle, "afdx", "data", 5*8 /*bits*/ );
AfdxSetTokenString( packetHandle, "afdx", "data", "Hello" );

// Complete and send packet
AfdxCompletePacket( packetHandle );
AfdxOutputPacket( packetHandle );

// release packet
AfdxReleasePacket( packetHandle );
```
