# J1939ILDelayTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILDelayTxTpEoma(long timeout);` //Form 1
- `long J1939ILDelayTxTpEoma(dbNode node, long timeout);` //Form 2

## Description

Delays transmitting of the TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is delayed every time until the CAPL function [J1939ILResetDelayedTxTpEoma](CAPLfunctionJ1939ILResetDelayedTxTpEoma.md) is called.

The delay time is added to the value set by [J1939ILSetNodeProperty("EoMALatency", …)](CAPLfunctionJ1939ILSetNodeProperty.md).

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
  res = J1939ILDelayTxTpEoma(200); // Delay TP.EoMA by 200 ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
