# J1939ILResetBlockedTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILResetBlockedTxTpEoma(); //Form 1`
- `long J1939ILResetBlockedTxTpEoma(dbNode node); //Form 2`

## Description

Resets all EoMA messages that were blocked with [J1939ILBlockTxTpEoma](CAPLfunctionJ1939ILBlockTxTpEoma.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = J1939ILBlockTxTpEoma(1); // Block the TP.EoMA message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = J1939ILResetBlockedTxTpEoma(); // Resets blocked TP.EoMA message.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
