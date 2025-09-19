[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILBlockTxTpDpo.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_BlockTxTpDpo

# FSIL_BlockTxTpDpo

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_BlockTxTpDpo( long dpoToBlock); //Form 1
long FSIL_BlockTxTpDpo( dbNode node, long dpoToBlock); //Form 2
```

## Description

Prevents transmitting of a ETP.DPO message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given DPO message is blocked every time until the CAPL function [FSIL_ResetBlockedTxTpDpo](CAPLfunctionIso11783FSILResetBlockedTxTpDpo.md) is called.

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
  res = FSIL_BlockTxTpDpo(1); // Block the first ETP.DPO message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
