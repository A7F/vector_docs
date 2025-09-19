[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Other/Functions/CAPLfunctionCanOffline.md)

[CAPL Functions](../../CAPLfunctions.md) » [General](../CAPLGeneralStartPage.md) » [Function Overview](../CAPLfunctionsGeneralOverview.md) » canOffline

# canOffline

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe:lite DE • CANoe4SW DE • CANoe4SW:lite DE

## Function Syntax

- ![Obsolete Function](../../../../Resources/Images/CAPLFunctions/ObsoleteFunction.png) `void canOffline();` // form 1: deprecated
- `dword canOffline(dword flags);` // form 2

## Description

Cuts the connection between the node and the bus. Messages sent from the node are not passed through to the bus. The function [canOnline()](CAPLfunctionCanOnline.md) will restore the connection.

If the node is set to offline, output instructions for sending messages in CAPL or modeling library are ignored (refers to a node locally only). Regardless of the status, all messages are received in the CAPL program/NodeLayer.

Form 1 only has an effect on the CAPL-program.

In form 2 you can choose between the CAPL-program and/or the Nodelayer-DLL.

## Parameters

- **Flags**: Indicates the deactivated part of the node.
  - `1`: Deactivates the CAPL-program
  - `2`: Deactivates the Nodelayer
  - `3`: Deactivates the CAPL-program and the Nodelayer and separates the diagnostic ECU simulation from the network, if one is configured for the node

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

[canOnline](CAPLfunctionCanOnline.md)

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
