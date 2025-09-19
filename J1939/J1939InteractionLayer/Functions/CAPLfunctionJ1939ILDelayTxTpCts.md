[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILDelayTxTpCts.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILDelayTxTpCts

# J1939ILDelayTxTpCts

[Valid for](../../../../Shared/FeatureAvailability.md):  CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILDelayTxTpCts(long ctsToDelay, long timeout); //Form 1
long J1939ILDelayTxTpCts(dbNode node, long ctsToDelay, long timeout); //Form 2
```

## Description

Delays transmitting of a TP.CTS message generated and sent by the interaction layer. The message to be delayed is identified by its occurrences on the bus, starting at 1. The given CTS message is delayed every time until the CAPL function [J1939ILResetDelayedTxTpCts](CAPLfunctionJ1939ILResetDelayedTxTpCts.md) is called.

The delay time is added to the value set by [J1939ILSetNodeProperty("CTSLatency", …)](CAPLfunctionJ1939ILSetNodeProperty.md).

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
  res = J1939ILDelayTxTpCts(2, 200); // Delay second TP.CTS by 200 ms.
  if(res != 0)
  {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
