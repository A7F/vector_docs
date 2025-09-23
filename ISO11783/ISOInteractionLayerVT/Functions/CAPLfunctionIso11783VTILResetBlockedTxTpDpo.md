[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxTpDpo.md)

**CAPL Functions** » **ISO11783** » **Virtual Terminal Interaction Layer (VT IL)** » **VTIL_ResetBlockedTxTpDpo**

# VTIL_ResetBlockedTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetBlockedTxTpDpo(); //Form 1`
- `long VTIL_ResetBlockedTxTpDpo( dbNode node); //Form 2`

## Description

Resets all DPO messages that were blocked with [VTIL_BlockTxTpDpo](CAPLfunctionIso11783VTILBlockTxTpDpo.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
// Reset blocked ETP.DPO messages by pressing ‘a’ on the keyboard.
on key 'a'{
  long res;
  res = VTIL_ResetBlockedTxTpDpo(); // Resets all blocked ETP.DPO messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
