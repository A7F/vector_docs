[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTFiAmsReceive.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostFiAmsReceive

# mostFiAmsReceive

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```
mostFiAmsReceive(mostAmsMessage * msg);
```

## Description

Simulates the receipt of an AMS message to the simulation node (CAPL program or node layer module).

`mostFiAmsReceive` can only be used within the callback [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md) or [OnMostFiAmsPreSend](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreSend.md). If `mostFiAmsReceive` is called more than once within the callback, only the last fed-in message is passed on to the simulation node.

Altered received messages are neither displayed in the Trace Window nor logged. They are only visible for the one node in the Simulation Setup from which `mostFiAmsReceive` was called.

**Exception**: a CAPL program with fault injection for the MOST application socket (see [mostAsFiEnable](CAPLfunctionMOSTAsFiEnable.md)) can call `mostFiAmsReceive` as many times as necessary and at any time in order to simulate a received message to the CANoe-side application socket. These altered messages are then visible only for the services of the MOST application socket in CANoe.

## Parameters

- **msg**: AMS message that is to be received by the simulation node.

## Return Values

—

## Example

See [OnMostFiAmsPreReceive](../EventProcedures/CAPLfunctionOnMOSTFiAmsPreReceive.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
