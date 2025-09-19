[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILBlockTxTpEoma.md)

**CAPL Functions** » **ISO11783** » **Task Controller Interaction Layer (TC IL)** » **TCIL_BlockTxTpEoma**

# TCIL_BlockTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long TCIL_BlockTxTpEoma(); //Form 1`
- `long TCIL_BlockTxTpEoma(dbNode node); //Form 2`

## Description

Prevents transmitting of the (E)TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is blocked every time until the CAPL function [TCIL_ResetBlockedTxTpEoma](CAPLfunctionIso11783TCILResetBlockedTxTpEoma.md) is called. After blocking the EoMA message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```c
on start {
  long res;
  res = TCIL_BlockTxTpEoma(1); // Block EoMA
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
