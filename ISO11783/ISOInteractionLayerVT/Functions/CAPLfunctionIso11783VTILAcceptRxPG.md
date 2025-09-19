[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILAcceptRxPG.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_AcceptRxPG**

# VTIL_AcceptRxPG

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_AcceptRxPG( pg * rxPG );
```

## Description

Checks if the received parameter group is addressed to the ISO11783 IL.

## Parameters

- **rxPG**: Receive parameter group

## Return Values

- **< 0**: [IL Error Code](../../../CAPLfunctionsISOj1939ErrorCodes.md)
- **0**: Parameter group is not address to the IL
- **1**: Parameter group is address to the IL

## Example

```plaintext
on pg TPRS
{
  if (VTIL_AcceptRxPG(this) <= 0) return;
  // ...
}
```

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
