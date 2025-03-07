[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILGetState.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_GetState

# Iso11783IL_GetState

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_GetState();` // form 1
- `long Iso11783IL_GetState(dbNode node);` // form 2

## Description

Returns the current state of the ISO11783 IL.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: Initialized
- **1**: Claiming
- **2**: Active
- **3**: Stopped
- **4**: Suspended
- **< 0**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)

## Example

```plaintext
on key 's'
{
  LONG state;
  state = Iso11783IL_GetState();
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)