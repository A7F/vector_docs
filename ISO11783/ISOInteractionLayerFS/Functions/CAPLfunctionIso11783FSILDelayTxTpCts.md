[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILDelayTxTpCts.md)

## FSIL_DelayTxTpCts

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_DelayTxTpCts

### Tool Availability
[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

### Function Syntax

- `long FSIL_DelayTxTpCts(long ctsToDelay, long timeout); //Form 1`
- `long FSIL_DelayTxTpCts(dbNode node, long ctsToDelay, long timeout); //Form 2`

### Description

Delays transmitting of a (E)TP.CTS message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given CTS message is delayed every time until the CAPL function [FSIL_ResetDelayedTxTpCts](CAPLfunctionIso11783FSILResetDelayedTxTpCts.md) is called.

The delay time is added to the value set by [FSIL_SetNodeProperty("CTSLatency", …)](CAPLfunctionIso11783FSILSetNodeProperty.md).

### Parameters

- **ctsToDelay**: The CTS message that shall be blocked [1…n].
- **timeout**: Delay in milliseconds [1…3600000].
- **node**: Simulation node to apply the function.

### Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **ctsToBlock** must be greater than 0
- **-3004**: Parameter **timeout** must be greater than 0

### Example

```plaintext
on start {
  long res;
  res = FSIL_DelayTxTpCts(2, 200); // Delay second TP.CTS by 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
