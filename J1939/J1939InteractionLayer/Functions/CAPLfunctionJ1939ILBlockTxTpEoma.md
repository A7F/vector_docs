[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILBlockTxTpEoma.md)

**CAPL Functions** » **J1939** » **J1939 IL** » J1939ILBlockTxTpEoma

# J1939ILBlockTxTpEoma

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long J1939ILBlockTxTpEoma(); //Form 1`
- `long J1939ILBlockTxTpEoma(dbNode node); //Form 2`

## Description

Prevents transmitting of the TP.EoMA (End Of Message Acknowledgement) message generated and sent by the interaction layer. The EoMA message is blocked every time until the CAPL function [J1939ILResetBlockedTxTpEoma](CAPLfunctionJ1939ILResetBlockedTxTpEoma.md) is called. After blocking the EoMA message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```c
on start {
  long res;
  res = J1939ILBlockTxTpEoma(1); // Block EoMA
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
