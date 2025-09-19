[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetProperty.md)

CAPL Functions » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPGetProperty

# Iso11783IL_OPGetProperty

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPGetProperty( char propertyName[] ); // form 1
long Iso11783IL_OPGetProperty( dbNode implement, char propertyName[] ); // form 2
```

## Description

Returns a property of the Object Pool API, e.g. the supported VT version.

## Parameters

- **propertyName**: Key of the information:
  - "Version": VT version support 2..4, Default 3
  - "DebugLevel": controls the output to the Write Window
    - 0: No output
    - 1: Only errors
    - 2: Warnings and errors
    - 3: Information, warnings and errors

- **implement**: Simulation node to apply the function.

## Return Values

- **≥ 0**: Value
- **< 0**: An error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-102**: Invalid parameter
- **-1113**: Unknown property

## Example

```plaintext
LONG version;
version = Iso11783IL_OPGetProperty( "Version" );
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
