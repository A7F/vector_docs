[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILBlockTxTpEoma.md)

**CAPL Functions** » **ISO11783** » **ISO11783 Interaction Layer** » Iso11783IL_BlockTxTpEoma

# Iso11783IL_BlockTxTpEoma

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long Iso11783IL_BlockTxTpEoma(); // Form 1
long Iso11783IL_BlockTxTpEoma(dbNode node); // Form 2
```

## Description

Prevents transmitting of the TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is blocked every time until the CAPL function [Iso11783IL_ResetBlockedTxTpEoma](CAPLfunctionIso11783ILResetBlockedTxTpEoma.md) is called. After blocking the EoMA message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_BlockTxTpEoma(1); // Block EoMA
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

**CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3**

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
