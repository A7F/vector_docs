[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTMessage.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » on mostMessage

# on mostMessage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`on mostMessage;`

## Description

The event procedure `on mostMessage` is called on the receipt of a function catalog conform MOST frame (RType=Normal).

The key word `this` and the message selectors (see [Selectors](../CAPLfunctionsMOSTOverview.md)) are available within the event procedures, to access the data of the message that has just been received. The command `output(this)` can be used for forwarding the message in a node chain.

## Parameters

—

## Return Values

—

## Example

The following examples show various modes of the event procedure `on mostMessage`:

- `on mostMessage AudioPlayer.TimePosition.Set`  
  React to message `AudioPlayer.TimePosition.Set` defined in a XML function catalog.
- `on mostMessage AudioPlayer_TimePosition_Set`  
  React to message `AudioPlayer_TimePosition_Set` defined in a CANdb database.
- `on mostMessage *`  
  React to all MOST messages
- `on mostMessage 0x312010`  
  React to message `0x312010` (function block 0x31, function 0x201, operation 0x0)
- `on mostMessage MsgChannel1.*`  
  React to all messages received by channel 1.
- `on mostMessage MsgChannel1.0x312010`  
  React to message `0x312010` if it is received by channel 1.
- `on mostMessage 0x22104C,0x312010-0x31201F`  
  React to messages `0x22104C` and `0x31201c` through `0x31201F`.

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)