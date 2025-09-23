# J1939ILDelayTxTpAbort

**Tool Availability:** [Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILDelayTxTpAbort(long timeout); //Form 1`
- `long J1939ILDelayTxTpAbort(dbNode node, long timeout); //Form 2`

## Description

Delays transmitting of the TP.Abort message generated and sent by the interaction layer. The Abort message is delayed every time until the CAPL function [J1939ILResetDelayedTxTpAbort](CAPLfunctionJ1939ILResetDelayededTxTpAbort.md) is called.

The delay time is added to the value set by [J1939ILSetNodeProperty("AbortLatency", …)](CAPLfunctionJ1939ILSetNodeProperty.md).

## Parameters

- **timeout**: Delay in milliseconds [1…3600000].
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3004**: Parameter **timeout** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = J1939ILDelayTxTpAbort(200); // Delay TP.Abort by 200ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
