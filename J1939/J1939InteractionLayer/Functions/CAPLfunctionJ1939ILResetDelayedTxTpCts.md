# J1939ILResetDelayedTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetDelayedTxTpCts(); //Form 1`
- `long J1939ILResetDelayedTxTpCts(dbNode node); //Form 2`

## Description

Resets all CTS messages that were blocked with [J1939ILDelayTxTpCts](CAPLfunctionJ1939ILDelayTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = J1939ILDelayTxTpCts(2, 200); // Delays second TP.CTS message for 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = J1939ILResetDelayedTxTpCts(); // Resets all delayed TP.CTS messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
