[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILBlockTxTpCts.md)

**CAPL Functions** » **J1939** » **J1939 IL** » **J1939ILBlockTxTpCts**

# J1939ILBlockTxTpCts

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

- `long J1939ILBlockTxTpCts(long ctsToBlock); //Form 1`
- `long J1939ILBlockTxTpCts(dbNode node, long ctsToBlock); //Form 2`

## Description

Prevents transmitting of a TP.CTS message generated and sent by the interaction layer. The message to be blocked is identified by its occurrences on the bus, starting at 1. The given CTS message is blocked every time until the CAPL function [J1939ILResetBlockedTxTpCts](CAPLfunctionJ1939ILResetBlockedTxTpCts.md) is called. After blocking the CTS message, the Interaction Layer silently closes the connection without sending further messages since the connection state is corrupted.

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
  res = J1939ILBlockTxTpCts(1); // Block the first CTS message
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
