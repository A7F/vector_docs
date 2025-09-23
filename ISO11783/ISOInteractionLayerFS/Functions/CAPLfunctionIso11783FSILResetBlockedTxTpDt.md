[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILResetBlockedTxTpDt.md)

**CAPL Functions** » **ISO11783** » **File Server Interaction Layer (FS IL)** » **FSIL_ResetBlockedTxTpDt**

# FSIL_ResetBlockedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_ResetBlockedTxTpDt();` //Form 1
- `long FSIL_ResetBlockedTxTpDt(dbNode node);` //Form 2

## Description

Resets all DT messages that were blocked with [FSIL_BlockTxTpDt](CAPLfunctionIso11783FSILBlockTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = FSIL_BlockTxTpDt(6, 4, 0); // Block 4 packets of the TP.DT message, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = FSIL_ResetBlockedTxTpDt(); // Resets blocked TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```
