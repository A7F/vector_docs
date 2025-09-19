[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939InteractionLayer/Functions/CAPLfunctionJ1939ILDelayTxTpDt.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 IL](../CAPLfunctionsJ1939ILOverview.md) » J1939ILDelayTxTpDt

# J1939ILDelayTxTpDt

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long J1939ILDelayTxTpDt(long firstMsg, long numOfMsg, long timeout); //Form 1
long J1939ILDelayTxTpDt(dbNode node, long firstMsg, long numOfMsg, long timeout); //Form 2
```

## Description

Delays transmitting of TP.DT messages generated and sent by the interaction layer. The messages to be delayed are identified by their occurrences on the bus, starting at 1 until the given message count is reached. The given range of DT messages are delayed every time until the CAPL function [J1939ILResetDelayedTxTpDt](CAPLfunctionJ1939ILResetDelayedTxTpDt.md) is called.

The delay time is added to the value set by [J1939ILSetNodeProperty("TPDTLatency", …)](CAPLfunctionJ1939ILSetNodeProperty.md).

## Parameters

- **firstMsg**: Sequence number of the first DT message that shall be blocked [1…n].
- **numOfMsg**: Number of DT messages that shall be blocked [1…n].
- **timeout**: The delay in milliseconds to continue the transmission with regularly sent DT messages [1…3600000].
- **node**: Simulation node to apply the function.

## Return Values

- **0**: OK
- **-3001**: General Error
- **-3002**: Parameter **firstMsg** must be greater than 0
- **-3003**: Parameter **numOfMsg** must be greater than 0

## Example

```plaintext
on start {
  long res;
  // Delay TP.DT packets 6, 7, 8, 9 by 200 ms each. Continue with packet no. 10 without delay.
  res = J1939ILDelayTxTpDt(6, 4, 200);
  if(res != 0) {
    write("An error occurred: %d", res);
  }
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
