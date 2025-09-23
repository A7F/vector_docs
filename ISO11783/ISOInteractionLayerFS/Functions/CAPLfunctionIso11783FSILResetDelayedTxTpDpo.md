[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetDelayedTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_ResetDelayedTxTpDpo

# FSIL_ResetDelayedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_ResetDelayedTxTpDpo(); //Form 1
long FSIL_ResetDelayedTxTpDpo( dbNode node); //Form 2
```

## Description

Resets all DPO messages that were blocked with [FSIL_DelayTxTpDpo](CAPLfunctionIso11783FSILDelayTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = FSIL_DelayTxTpDpo(1, 2, 20); // Delay the first two ETP.DPO messages for 20 ms
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = FSIL_ResetDelayedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
