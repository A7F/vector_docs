[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetBlockedTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetBlockedTxTpCts

# TCIL_ResetBlockedTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetBlockedTxTpCts();` //Form 1
- `long TCIL_ResetBlockedTxTpCts(dbNode node);` //Form 2

## Description

Resets all CTS messages that were blocked with [TCIL_BlockTxTpCts](CAPLfunctionIso11783TCILBlockTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked TP.CTS messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = TCIL_ResetBlockedTxTpCts(); // Resets all blocked TP.CTS messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
