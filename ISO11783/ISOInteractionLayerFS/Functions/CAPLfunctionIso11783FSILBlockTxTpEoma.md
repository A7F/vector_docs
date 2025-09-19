[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILBlockTxTpEoma.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_BlockTxTpEoma

# FSIL_BlockTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

- `long FSIL_BlockTxTpEoma(); //Form 1`
- `long FSIL_BlockTxTpEoma(dbNode node); //Form 2`

## Description

Prevents transmitting of the (E)TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is blocked every time until the CAPL function [FSIL_ResetBlockedTxTpEoma](CAPLfunctionIso11783FSILResetBlockedTxTpEoma.md) is called. After blocking the EoMA message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = FSIL_BlockTxTpEoma(1); // Block EoMA
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
