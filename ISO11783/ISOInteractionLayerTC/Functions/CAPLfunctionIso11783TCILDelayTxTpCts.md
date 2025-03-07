[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/ISO11783/ISOInteractionLayerTC/Functions/CAPLfunctionIso11783TCILDelayTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [ISO11783](../../CAPLfunctionsISO11783Overview.md) » [Task Controller Interaction Layer (TC IL)](../CAPLfunctionsISOILTCOverview.md) » TCIL_DelayTxTpCts

# TCIL_DelayTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long TCIL_DelayTxTpCts(long ctsToDelay, long timeout); //Form 1
long TCIL_DelayTxTpCts(dbNode node, long ctsToDelay, long timeout); //Form 2
```

## Description

Delays transmitting of a (E)TP.CTS message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given CTS message is delayed every time until the CAPL function [TCIL_ResetDelayedTxTpCts](CAPLfunctionIso11783TCILResetDelayedTxTpCts.md) is called.

The delay time is added to the value set by [TCIL_SetNodeProperty("CTSLatency", …)](CAPLfunctionIso11783TCILSetNodeProperty.md).

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
  res = TCIL_DelayTxTpCts(2, 200); // Delay second TP.CTS by 200 ms.
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)