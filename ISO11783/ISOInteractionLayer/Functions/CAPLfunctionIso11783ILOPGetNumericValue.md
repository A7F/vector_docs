[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPGetNumericValue.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » **Iso11783IL_OPGetNumericValue**

# Iso11783IL_OPGetNumericValue

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPGetNumericValue( dword objectID, long& value ); // form 1`
- `long Iso11783IL_OPGetNumericValue( dbNode implement, dword objectID, long& value ); // form 2`
- `long Iso11783IL_OPGetNumericValue( dword objectID ); // form 3 **deprecated**`
- `long Iso11783IL_OPGetNumericValue( dbNode implement, dword objectID ); // form 4 **deprecated**`

## Description

The function returns a numeric value of an object. The object must exist in the object pool and must support a numeric value.

## Parameters

- **objectID**: Object Identifier of the object.
- **implement**: Simulation node to apply the function.
- **value**: Returns the integer value of the object.

## Return Values

- **Form 1, 2**: 0 on success or [error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **Form 3, 4**: Integer value of the object. If a value of 0 is returned, you can check with the function [Iso11783IL_GetLastError](CAPLfunctionIso11783ILGetLastError.md) if the function succeeded.

## Example

```plaintext
LONG val, result
result = Iso11783IL_OPGetNumericValue( 1000, value);
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
