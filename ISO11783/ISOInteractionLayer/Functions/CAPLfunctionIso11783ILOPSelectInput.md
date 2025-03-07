[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILOPSelectInput.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_OPSelectInput

# Iso11783IL_OPSelectInput

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_OPSelectInput( dword objectID, dword select ); // form 1
long Iso11783IL_OPSelectInput( dbNode implement, dword objectID, dword select ); // form 2
```

## Description

The function selects an input object. A **Select Input** command is sent to the Virtual Terminal.

## Parameters

- **objectID**: object ID of an input object
- **select**:
  - 0: no input object shall be selected (i.e. focus is removed)
  - 1: select input object
  - 2: open input object for user input (only version >= 3)
- **implement**: Simulation node to apply the function.

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred, see [error codes](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
Iso11783IL_OPSelectInput( 1200, 1 );
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)