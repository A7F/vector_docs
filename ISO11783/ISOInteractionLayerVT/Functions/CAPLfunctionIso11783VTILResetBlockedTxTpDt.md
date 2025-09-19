[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetBlockedTxTpDt.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetBlockedTxTpDt

# VTIL_ResetBlockedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetBlockedTxTpDt();` //Form 1
- `long VTIL_ResetBlockedTxTpDt(dbNode node);` //Form 2

## Description

Resets all DT messages that were blocked with [VTIL_BlockTxTpDt](CAPLfunctionIso11783VTILBlockTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpDt(6, 4, 0); // Block 4 packets of the TP.DT message, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = VTIL_ResetBlockedTxTpDt(); // Resets blocked TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
