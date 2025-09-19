[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILAcceptRxPG.md)

**CAPL Functions** » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILAcceptRxPG

# J1939ILAcceptRxPG

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long J1939ILAcceptRxPG( pg * rxPG )
```

## Description

Checks if the received parameter group is addressed to the J1939 IL.

## Parameters

- **rxPG**: receive parameter group

## Return Values

- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **0**: parameter group is not addressed to the IL
- **1**: parameter group is addressed to the IL

## Example

```plaintext
on pg TPRS
{
  if (J1939ILAcceptRxPG( this ) <= 0) return;
  // ...
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
