[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxTpEoma.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetBlockedTxTpEoma

# VTIL_ResetBlockedTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_ResetBlockedTxTpEoma(); //Form 1
long VTIL_ResetBlockedTxTpEoma(dbNode node); //Form 2
```

## Description

Resets all EoMA messages that were blocked with [VTIL_BlockTxTpEoma](CAPLfunctionIso11783VTILBlockTxTpEoma.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpEoma(1); // Block the TP.EoMA message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = VTIL_ResetBlockedTxTpEoma(); // Resets blocked TP.EoMA message.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
