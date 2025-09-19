[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetStringValue.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPGetStringValue

# Iso11783IL_OPGetStringValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPGetStringValue( dword objectID, dword bufferSize, char buffer[] ); // form 1: deprecated.`
- `long Iso11783IL_OPGetStringValue( dword objectID, char buffer[] ); // form 2`
- `long Iso11783IL_OPGetStringValue( dbNode implement, dword objectID, dword bufferSize, char buffer[] ); // form 3: deprecated.`
- `long Iso11783IL_OPGetStringValue( dbNode implement, dword objectID, char buffer[] ); // form 4`

## Description

The function copies a string value of an object in the object pool into a buffer. The object must exist in the object pool and support a string value.

## Parameters

- **objectID**: object Identifier of the object
- **bufferSize**: size of the string buffer
- **buffer**: string buffer in which the string is copied
- **implement**: Simulation node to apply the function.

## Return Values

- **≥ 0**: number of copied characters
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-1110**: object ID does not exist
- **-1112**: string Value not supported

## Example

```c
char buffer[100];
Iso11783IL_OPGetStringValue( 1000, buffer );
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
