[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILAcceptRxPG.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_AcceptRxPG

# Iso11783IL_AcceptRxPG

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_AcceptRxPG( pg * rxPG ); // form 1`
- `long Iso11783IL_AcceptRxPG( dbNode node,  pg * rxPG ); // from 2`

## Description

Checks if the received parameter group is addressed to the ISO11783 IL.

## Parameters

- **rxPG**: Receive parameter group.
- **node**: Simulation node to apply the function.

## Return Values

- **< 0**: [Error code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **0**: Parameter group is not address to the IL
- **1**: Parameter group is address to the IL

## Example

```plaintext
on pg TPRS
{
  if (Iso11783IL_AcceptRxPG( this ) <= 0) return;
  // ...
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
