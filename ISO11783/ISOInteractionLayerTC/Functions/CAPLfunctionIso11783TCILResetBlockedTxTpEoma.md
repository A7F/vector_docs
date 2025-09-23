[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetBlockedTxTpEoma.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetBlockedTxTpEoma

# TCIL_ResetBlockedTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetBlockedTxTpEoma();` //Form 1
- `long TCIL_ResetBlockedTxTpEoma(dbNode node);` //Form 2

## Description

Resets all EoMA messages that were blocked with [TCIL_BlockTxTpEoma](CAPLfunctionIso11783TCILBlockTxTpEoma.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_BlockTxTpEoma(1); // Block the TP.EoMA message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = TCIL_ResetBlockedTxTpEoma(); // Resets blocked TP.EoMA message.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
