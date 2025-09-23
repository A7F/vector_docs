[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILBlockTxTpCts.md)

**CAPL Functions** » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_BlockTxTpCts

# Iso11783IL_BlockTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long Iso11783IL_BlockTxTpCts( long ctsToBlock); //Form 1
long Iso11783IL_BlockTxTpCts( dbNode node, long ctsToBlock); //Form 2
```

## Description

Prevents transmitting of a (E)TP.CTS message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given CTS message is blocked every time until the CAPL function [Iso11783IL_ResetBlockedTxTpCts](CAPLfunctionIso11783ILResetBlockedTxTpCts.md) is called. After blocking the CTS message, the Interaction Layer silently closes the connection without sending further messages since the connection state is corrupted.

## Parameters

- **ctsToBlock**: The CTS message that shall be blocked.
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **ctsToBlock** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```
