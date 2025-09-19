[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPEnableObject.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPEnableObject

# Iso11783IL_OPEnableObject

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPEnableObject( dword objectID, dword enable ); // form 1
long Iso11783IL_OPEnableObject( dbNode implement, dword objectID, dword enable ); // form 2
```

## Description

The function activates or deactivates an input object. A **Enable Object** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: object ID of an input object
- **enable**:
  - 1: activate
  - 0: deactivate
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPEnableObject( 1200, 1 );
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
