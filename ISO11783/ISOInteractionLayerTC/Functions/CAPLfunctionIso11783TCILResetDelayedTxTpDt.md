[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetDelayedTxTpDt.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetDelayedTxTpDt

# TCIL_ResetDelayedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetDelayedTxTpDt(); //Form 1`
- `long TCIL_ResetDelayedTxTpDt(dbNode node); //Form 2`

## Description

Resets all DT messages that were delayed with [TCIL_DelayTxTpDt](CAPLfunctionIso11783TCILDelayTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_DelayTxTpDt(6, 4, 200); // Delays four TP.DT messages by 200 ms, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = TCIL_ResetDelayedTxTpDt(); // Resets all delayed TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
