[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDelayTxTpAbort.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_DelayTxTpAbort

# FSIL_DelayTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_DelayTxTpAbort(long timeout); //Form 1`
- `long FSIL_DelayTxTpAbort(dbNode node, long timeout); //Form 2`

## Description

Delays transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is delayed every time until the CAPL function [FSIL_ResetDelayedTxTpAbort](CAPLfunctionIso11783FSILResetDelayededTxTpAbort.md) is called.

The delay time is added to the value set by [FSIL_SetNodeProperty("AbortLatency", …)](CAPLfunctionIso11783FSILSetNodeProperty.md).

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
  res = FSIL_DelayTxTpAbort(200); // Delay TP.Abort by 200ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
