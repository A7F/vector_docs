[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ADFX/Functions/CAPLfunctionAfdxRemoveToken.md)

**CAPL Functions** » **AFDX** » **AfdxRemoveToken**

# AfdxRemoveToken

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

```plaintext
long AfdxRemoveToken( long packet, char protocolDesignator[], char tokenDesignator[] );
```

## Description

This function removes a token from a protocol header.

## Parameters

- **packet**: Handle of the message that has been created with [AfdxInitPacket](CAPLfunctionAfdxInitPacket.md).
- **protocolDesignator**: Name of the [protocol](../../../CANoeCANalyzer/AFDX/protocols/afdxProtocolsIntro.md).
- **tokenDesignator**: Name of the token.

## Return Values

- **0**: 
- **other value**: [error code](../CAPLfunctionsAFDXErrorCodes.md)

## Example

—

[See Also](javascript:void(0);)