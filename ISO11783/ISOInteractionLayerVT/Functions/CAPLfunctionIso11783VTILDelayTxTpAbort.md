[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILDelayTxTpAbort.md)

## VTIL_DelayTxTpAbort

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_DelayTxTpAbort

### Tool Availability

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

### Function Syntax

- `long VTIL_DelayTxTpAbort(long timeout); //Form 1`
- `long VTIL_DelayTxTpAbort(dbNode node, long timeout); //Form 2`

### Description

Delays transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is delayed every time until the CAPL function [VTIL_ResetDelayedTxTpAbort](CAPLfunctionIso11783VTILResetDelayededTxTpAbort.md) is called.

The delay time is added to the value set by [VTIL_SetNodeProperty("AbortLatency", …)](CAPLfunctionIso11783VTILSetNodeProperty.md).

### Parameters

- **timeout**: Delay in milliseconds [1…3600000].
- **node**: Simulation node to apply the function.

### Return Values

- **0**: OK
- **-3001**: General Error
- **-3004**: Parameter **timeout** must be greater than 0

### Example

```plaintext
on start {
  long res;
  res = VTIL_DelayTxTpAbort(200); // Delay TP.Abort by 200ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
