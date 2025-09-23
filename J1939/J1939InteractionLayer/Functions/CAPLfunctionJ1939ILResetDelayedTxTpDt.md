# J1939ILResetDelayedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetDelayedTxTpDt(); //Form 1`
- `long J1939ILResetDelayedTxTpDt(dbNode node); //Form 2`

## Description

Resets all DT messages that were delayed with [J1939ILDelayTxTpDt](CAPLfunctionJ1939ILDelayTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```c
on start {
  long res;
  res = J1939ILDelayTxTpDt(6, 4, 200); // Delays four TP.DT messages by 200 ms, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = J1939ILResetDelayedTxTpDt(); // Resets all delayed TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
