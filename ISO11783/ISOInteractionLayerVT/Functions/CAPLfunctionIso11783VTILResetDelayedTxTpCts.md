[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetDelayedTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetDelayedTxTpCts

# VTIL_ResetDelayedTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_ResetDelayedTxTpCts(); //Form 1`
- `long VTIL_ResetDelayedTxTpCts(dbNode node); //Form 2`

## Description

Resets all CTS messages that were blocked with [VTIL_DelayTxTpCts](CAPLfunctionIso11783VTILDelayTxTpCts.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_DelayTxTpCts(2, 200); // Delays second TP.CTS message for 200 ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = VTIL_ResetDelayedTxTpCts(); // Resets all delayed TP.CTS messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
