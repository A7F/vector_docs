[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerFS/Functions/CAPLfunctionIso11783FSILBlockTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [File Server Interaction Layer (FS IL)](../CAPLfunctionsISOILFSOverview.md) » FSIL_BlockTxTpCts

# FSIL_BlockTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long FSIL_BlockTxTpCts(long ctsToBlock); //Form 1
long FSIL_BlockTxTpCts(dbNode node, long ctsToBlock); //Form 2
```

## Description

Prevents transmitting of a (E)TP.CTS message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given CTS message is blocked every time until the CAPL function [FSIL_ResetBlockedTxTpCts](CAPLfunctionIso11783FSILResetBlockedTxTpCts.md) is called. After blocking the CTS message, the Interaction Layer silently closes the connection without sending further messages since the connection state is corrupted.

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
  res = FSIL_BlockTxTpCts(1); // Block the first CTS message
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
