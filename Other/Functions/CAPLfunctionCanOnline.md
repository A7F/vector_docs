[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCanOnline.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » canOnline

# canOnline

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- `void canOnline();` // form 1: deprecated
- `dword canOnline(dword flags);` // form 2

## Description

Restores the connection of the node to the bus. After a call to the function `canOffline()` the node can be connected to the bus with the function `canOnline()`. Messages sent from the node are passed through to the bus.

If the node is set to offline, output instructions for sending messages in CAPL or modeling library are ignored (refers to a node locally only). Regardless of the status, all messages are received in the CAPL program/NodeLayer.

Form 1 only has an effect on the CAPL-program.

In form 2 you can choose between the CAPL-program and/or the Nodelayer-DLL.

## Parameters

- **Flags**: Indicates the activated part of the node.
  - `1`: Activates the CAPL-program
  - `2`: Activates the Nodelayer
  - `3`: Activates the CAPL-program and the Nodelayer and attaches the diagnostic ECU simulation to the network, if one is configured for the node

## Return Values

Form 2 returns the part of the node being online before the function call. Equal to the flags.

## Example

```plaintext
dword var;
var = canOffline(3); // Deactivates CAPL-Program and Nodelayer-DLL.
...
canOnline(); // Activates CAPL-Program. Form 1
...
var = canOnline(2); // Activates Nodelayer-DLL
```

[canOffline](CAPLfunctionCanOffline.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
