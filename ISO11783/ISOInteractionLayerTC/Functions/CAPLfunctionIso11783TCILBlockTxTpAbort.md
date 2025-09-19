[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILBlockTxTpAbort.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_BlockTxTpAbort

# TCIL_BlockTxTpAbort

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_BlockTxTpAbort( ); //Form 1
long TCIL_BlockTxTpAbort( dbNode node); //Form 2
```

## Description

Prevents transmitting of the (E)TP.Abort message generated and sent by the interaction layer. The Abort message is blocked every time until the CAPL function [TCIL_ResetBlockedTxTpAbort](CAPLfunctionIso11783TCILResetBlockedTxTpAbort.md) is called. After blocking the Abort message, the Interaction Layer silently closes the connection without sending further messages.

## Parameters

- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error

## Example

```plaintext
on start {
  long res;
  res = TCIL_BlockTxTpAbort(1); // Block Abort
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
