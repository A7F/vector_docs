[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTAMSMessage.md)

## CAPL Functions » MOST » on mostAMSMessage

### Function Syntax

`on mostAMSMessage;`

### Description

The event procedure `on mostAMSMessage` is called when a message is received from the Application Message Service (AMS).

The keyword `this` and the [message selectors](../CAPLfunctionsMOSTOverview.md) are available within event procedures to permit access to the data of the message just received. The `output(this)` command serves to pass the message in a nodal sequence.

The same modes of the event procedure as for on [mostMessage](CAPLfunctionOnMOSTMessage.md) may be used to prefilter messages.

### Parameters

—

### Return Values

—

### Example

The following examples show various modes of the event procedure `on mostAMSMessage`:

- `on mostAMSMessage AudioPlayer.TimePosition.Set`  
  React to message `AudioPlayer.TimePosition.Set` defined in a XML function catalog.

- `on mostAMSMessage AudioPlayer_TimePosition_Set`  
  React to message `AudioPlayer_TimePosition_Set` defined in a CANdb database.

- `on mostAMSMessage *`  
  React to all MOST messages

- `on mostAMSMessage 0x312010`  
  React to message `0x312010` (function block 0x31, function 0x201, operation 0x0)

- `on mostAMSMessage MsgChannel1.*`  
  React to all messages received by channel 1.

- `on mostAMSMessage MsgChannel1.0x312010`  
  React to message `0x312010` if it is received by channel 1.

- `on mostAMSMessage 0x22104C,0x312010-0x31201F`  
  React to messages `0x22104C` and `0x31201c` through `0x31201F`.

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
