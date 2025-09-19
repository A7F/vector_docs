[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSetNumericValue.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSetNumericValue

# Iso11783IL_OPSetNumericValue

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_OPSetNumericValue( dword objectID, long numericValue ); // form 1`
- `long Iso11783IL_OPSetNumericValue( dword objectID, long numericValue, long options ); // form 2`
- `long Iso11783IL_OPSetNumericValue( dbNode implement, dword objectID, long numericValue, long options ); // form 3`

## Description

The function sets the numerical value of an object. The object must exist in the object pool and must support a numerical value. If the Object Pool API is active, a **Change Numeric Value** command is sent to the Virtual Terminal. This can be suppressed with Bit 0 in options.

## Parameters

- **objectID**: object ID of the object that has an updated value
- **numericValue**: new value within the value range of the object
- **options**: options
  - Bit 0 and 1 = 0: send **Change Numeric Value** command if parameters are valid
  - Bit 0 and 1 = 1: suppress **Change Numeric Value** command
  - Bit 0 and 1 = 2: force sending **Change Numeric Value** command even parameters are invalid
  - Bit 0 and 1 = 3: reserved
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPSetNumericValue( 1000, 100 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
