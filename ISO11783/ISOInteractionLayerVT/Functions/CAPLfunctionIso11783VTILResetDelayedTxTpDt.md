[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILResetDelayedTxTpDt.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_ResetDelayedTxTpDt

# VTIL_ResetDelayedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long VTIL_ResetDelayedTxTpDt(); //Form 1
long VTIL_ResetDelayedTxTpDt(dbNode node); //Form 2
```

## Description

Resets all DT messages that were delayed with [VTIL_DelayTxTpDt](CAPLfunctionIso11783VTILDelayTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_DelayTxTpDt(6, 4, 200); // Delays four TP.DT messages by 200 ms, starting with packet no. 6.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = VTIL_ResetDelayedTxTpDt(); // Resets all delayed TP.DT messages.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
