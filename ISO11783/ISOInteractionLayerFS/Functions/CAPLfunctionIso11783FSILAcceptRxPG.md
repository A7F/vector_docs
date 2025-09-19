[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILAcceptRxPG.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_AcceptRxPG

# FSIL_AcceptRxPG

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_AcceptRxPG( pg * rxPG );
```

## Description

Checks if the received parameter group is addressed to the FS IL.

## Parameters

- **rxPG**: Receive parameter group

## Return Values

- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **0**: Parameter group is not addressed to the IL
- **1**: Parameter group is addressed to the IL

## Example

```plaintext
on pg TPRS
{
  if (FSIL_AcceptRxPG( this ) <= 0) return;
  // ...
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
