[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILResetBlockedTxTpDt.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_ResetBlockedTxTpDt

# TCIL_ResetBlockedTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_ResetBlockedTxTpDt(); //Form 1`
- `long TCIL_ResetBlockedTxTpDt(dbNode node); //Form 2`

## Description

Resets all DT messages that were blocked with [TCIL_BlockTxTpDt](CAPLfunctionIso11783TCILBlockTxTpDt.md).

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-1**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_BlockTxTpDt(6, 4, 0); // Block 4 packets of the TP.DT message, starting with packet no. 6.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
on key 'a'{
  long res;
  res = TCIL_ResetBlockedTxTpDt(); // Resets blocked TP.DT messages.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
