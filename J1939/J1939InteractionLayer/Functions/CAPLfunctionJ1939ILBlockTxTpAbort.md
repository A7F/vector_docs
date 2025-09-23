# J1939ILBlockTxTpAbort

[Feature availability for your product](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILBlockTxTpAbort();` // Form 1
- `long J1939ILBlockTxTpAbort(dbNode node);` // Form 2

### Description

Prevents transmitting of the TP.Abort message generated and sent by the interaction layer. The Abort message is blocked every time until the CAPL function [J1939ILResetBlockedTxTpAbort](CAPLfunctionJ1939ILResetBlockedTxTpAbort.md) is called. After blocking the Abort message, the Interaction Layer silently closes the connection without sending further messages.

### Parameters

- **node**: Simulation node to apply the function.

### Return Values

- **0**: OK
- **-3001**: General Error

### Example

```plaintext
on start {
  long res;
  res = J1939ILBlockTxTpAbort(1); // Block Abort
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
