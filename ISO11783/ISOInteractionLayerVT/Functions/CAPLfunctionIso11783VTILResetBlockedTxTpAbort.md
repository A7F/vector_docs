[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxTpAbort.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetBlockedTxTpAbort

# VTIL_ResetBlockedTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetBlockedTxTpAbort(); //Form 1`
- `long VTIL_ResetBlockedTxTpAbort(dbNode node); //Form 2`

## Description

Resets all CTS messages that were blocked with [VTIL_BlockTxTpAbort](CAPLfunctionIso11783VTILBlockTxTpAbort.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpAbort(); // Block the TP.Abort message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a' {
  long res;
  res = VTIL_ResetBlockedTxTpAbort(); // Resets blocked TP.Abort message.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
