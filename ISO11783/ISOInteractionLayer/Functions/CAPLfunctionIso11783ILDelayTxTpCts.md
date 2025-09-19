[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayer/Functions/CAPLfunctionIso11783ILDelayTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [ISO11783 Interaction Layer](../CAPLfunctionsISOILOverview.md) » Iso11783IL_DelayTxTpCts

# Iso11783IL_DelayTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

- `long Iso11783IL_DelayTxTpCts(long ctsToDelay, long timeout); //Form 1`
- `long Iso11783IL_DelayTxTpCts(dbNode node, long ctsToDelay, long timeout); //Form 2`

## Description

Delays transmitting of a TP.CTS message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given CTS message is delayed every time until the CAPL function [Iso11783IL_ResetDelayedTxTpCts](CAPLfunctionIso11783ILResetDelayedTxTpCts.md) is called.

The delay time is added to the value set by [Iso11783IL_SetNodeProperty("CTSLatency", …)](CAPLfunctionIso11783ILSetNodeProperty.md).

## Parameters

- **ctsToDelay**: The CTS message that shall be blocked [1…n].
- **timeout**: Delay in milliseconds [1…3600000].
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **ctsToBlock** must be greater than 0
- **-3004**: Parameter **timeout** must be greater than 0

## Example

```plaintext
on start {
  long res;
  res = Iso11783IL_DelayTxTpCts(2, 200); // Delay second TP.CTS by 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
