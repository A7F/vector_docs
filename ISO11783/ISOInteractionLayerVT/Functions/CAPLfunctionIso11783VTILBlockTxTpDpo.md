[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILBlockTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_BlockTxTpDpo

# VTIL_BlockTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_BlockTxTpDpo(long dpoToBlock); //Form 1`
- `long VTIL_BlockTxTpDpo(dbNode node, long dpoToBlock); //Form 2`

## Description

Prevents transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given DPO message is blocked every time until the CAPL function [VTIL_ResetBlockedTxTpDpo](CAPLfunctionIso11783VTILResetBlockedTxTpDpo.md) is called.

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
  res = VTIL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
