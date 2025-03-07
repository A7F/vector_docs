[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILBlockTxTpAbort.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_BlockTxTpAbort

# Iso11783IL_BlockTxTpAbort

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_BlockTxTpAbort(); //Form 1`
- `long Iso11783IL_BlockTxTpAbort(dbNode node); //Form 2`

## Description

Prevents transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is blocked every time until the CAPL function [Iso11783IL_ResetBlockedTxTpAbort](CAPLfunctionIso11783ILResetBlockedTxTpAbort.md) is called. After blocking the Abort message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_BlockTxTpAbort(1); // Block Abort
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)