[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILDelayTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_DelayTxTpDpo

# TCIL_DelayTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_DelayTxTpDpo( long dpoToBlock); //Form 1
long TCIL_DelayTxTpDpo( dbNode node, long dpoToBlock); //Form 2
```

## Description

Delays transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given DPO message is delayed every time until the CAPL function [TCIL_ResetDelayedTxTpDpo](CAPLfunctionIso11783TCILResetDelayedTxTpDpo.md) is called.

## Parameters

- **dpoToBlock**: The ETP.DPO message that shall be blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **dpoToBlock** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = TCIL_DelayTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
