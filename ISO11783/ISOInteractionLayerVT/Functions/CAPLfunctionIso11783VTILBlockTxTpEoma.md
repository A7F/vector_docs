[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerVT/Functions/CAPLfunctionIso11783VTILBlockTxTpEoma.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Virtual Terminal Interaction Layer (VT IL)](../CAPLfunctionsISOILVTOverview.md) » VTIL_BlockTxTpEoma

# VTIL_BlockTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long VTIL_BlockTxTpEoma(); //Form 1`
- `long VTIL_BlockTxTpEoma(dbNode node); //Form 2`

## Description

Prevents transmitting of the (E)TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is blocked every time until the CAPL function [VTIL_ResetBlockedTxTpEoma](CAPLfunctionIso11783VTILResetBlockedTxTpEoma.md) is called. After blocking the EoMA message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = VTIL_BlockTxTpEoma(1); // Block EoMA
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)