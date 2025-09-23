# J1939ILResetBlockedTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetBlockedTxTpAbort(); //Form 1`
- `long J1939ILResetBlockedTxTpAbort(dbNode node); //Form 2`

## Description

Resets all CTS messages that were blocked with [J1939ILBlockTxTpAbort](CAPLfunctionJ1939ILBlockTxTpAbort.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = J1939ILBlockTxTpAbort(); // Block the TP.Abort message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = J1939ILResetBlockedTxTpAbort(); // Resets blocked TP.Abort message.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
