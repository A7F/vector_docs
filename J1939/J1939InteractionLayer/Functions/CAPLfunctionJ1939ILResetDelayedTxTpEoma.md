# J1939ILResetDelayedTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetDelayedTxTpEoma(); //Form 1`
- `long J1939ILResetDelayedTxTpEoma(dbNode node); //Form 2`

## Description

Resets all EoMA messages that were delayed with [J1939ILDelayTxTpEoma](CAPLfunctionJ1939ILDelayTxTpEoma.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = J1939ILDelayTxTpEoma(200); // Delays TP.EoMA message for 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a' {
  long res;
  res = J1939ILResetDelayedTxTpEoma(); // Resets delayed TP.EoMA message.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
