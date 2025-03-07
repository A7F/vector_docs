[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILBlockTxTpDpo.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_BlockTxTpDpo

# Iso11783IL_BlockTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_BlockTxTpDpo(long dpoToBlock); //Form 1`
- `long Iso11783IL_BlockTxTpDpo(dbNode node, long dpoToBlock); //Form 2`

## Description

Prevents transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given DPO message is blocked every time until the CAPL function [ISO11783IL_ResetBlockedTxTpDpo](CAPLfunctionIso11783ILResetBlockedTxTpDpo.md) is called.

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
  res = Iso11783IL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)