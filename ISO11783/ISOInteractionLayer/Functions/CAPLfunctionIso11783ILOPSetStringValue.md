[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSetStringValue.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSetStringValue

# Iso11783IL_OPSetStringValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPSetStringValue( dword objectID, char stringValue[] ); // form 1`
- `long Iso11783IL_OPSetStringValue( dword objectID, char stringValue[], dword options ); // form 2`
- `long Iso11783IL_OPSetStringValue( dbNode implement, dword objectID, char stringValue[], dword options, dword encodingBehavior ); // form 3`
- `long Iso11783IL_OPSetStringValue( dbNode implement, dword objectID, char stringValue[], dword options ); // form 4`
- `long Iso11783IL_OPSetStringValue( dbNode implement, dword objectID, char stringValue[], dword options, dword encodingBehavior ); // form 5`

## Description

The functions set the string value of an object in the object pool. The object must exist in the object pool and must support a string value. If the Object Pool API is active, a **Change String Value** command is sent to the Virtual Terminal. This can be suppressed with Bit 0 in **options**.

Forms 1, 2, and 4 store the string as an 8-bit string. Forms 3 and 5 allow you to specify whether to encode the string as an 8-bit or 16-bit string. For 16-bit strings, the byte order mark (BOM) character 0xFEFF is inserted at the beginning.

## Parameters

- **objectID**: object ID of the object that has an updated value
- **stringValue**: buffer containing new string value
- **options**: options
  - Bit 0 and 1 = 0: send **Change String Value** command if parameters are valid
  - Bit 0 and 1 = 1: suppress **Change String Value** command
  - Bit 0 and 1 = 2: force sending **Change String Value** command even parameters are invalid
  - Bit 0 and 1 = 3: reserved
- **encodingBehavior**: Specifies the encoding of the string value to be set.
  - 0: Encode string to 8-bit character string
  - 1: Encode string to 16-bit character string (WideString)
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **-1109**: string is read only
- **-1110**: object ID not found
- **-1112**: string Value not supported

## Example

```plaintext
Iso11783IL_OPSetStringValue( 1000, "Hello World" );
```
