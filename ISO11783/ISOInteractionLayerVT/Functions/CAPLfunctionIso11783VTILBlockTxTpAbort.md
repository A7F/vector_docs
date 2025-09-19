[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILBlockTxTpAbort.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_BlockTxTpAbort

# VTIL_BlockTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_BlockTxTpAbort(); //Form 1`
- `long VTIL_BlockTxTpAbort(dbNode node); //Form 2`

## Description

Prevents transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is blocked every time until the CAPL function [VTIL_ResetBlockedTxTpAbort](CAPLfunctionIso11783VTILResetBlockedTxTpAbort.md) is called. After blocking the Abort message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpAbort(1); // Block Abort
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
