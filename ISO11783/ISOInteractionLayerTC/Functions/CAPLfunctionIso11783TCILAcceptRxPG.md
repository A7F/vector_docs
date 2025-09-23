[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILAcceptRxPG.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_AcceptRxPG**

# TCIL_AcceptRxPG

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_AcceptRxPG( pg * rxPG );
```

## Description

Checks if the received parameter group is addressed to the TC IL.

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
  if (TCIL_AcceptRxPG(this) <= 0) return;
  // ...
}
```
