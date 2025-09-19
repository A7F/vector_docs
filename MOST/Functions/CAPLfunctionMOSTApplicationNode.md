[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTApplicationNode.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostApplicationNode

# mostApplicationNode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
void mostApplicationNode();
```

## Description

This CAPL function can only be called in `on preStart` and switches the CAPL node into application mode. The node will:

- not receive Spy messages any more,
- only receive messages (mostMessages, mostAmsMessage) from channels to which it is connected in the Simulation Setup and
- send messages on the channel to which it is connected in the Simulation Setup

**Note**

This mode is especially useful for nodes connected to a single MOST channel in the Simulation Setup. Checks like "if (this.MsgChannel!=XY) return;" or "if (this.IsSpy()) return;" or event handler "on mostMessage MsgChannel1.*" explicit for a channel can be omitted. In many cases the assignment of a channel before sending a message can be omitted. With declaration of a message variable the channel will be initialized with a wildcard (0xFFFF), which will be mapped to the channel with which the node is connected in the Simulation Setup on transmission. This makes the CAPL code easily reusable because it is independent of any hard coded channel numbers. The application mode is independent of the activation of the application socket, however it especially utilizes the implementation of function block behavior.

## Parameters

—

## Return Values

—

## Example

—

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
