[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetThisMessage.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » getThisMessage

# getThisMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

`GetThisMessage(mostAMSMessage msg, long count);`

## Description

Copies the data of an AMS message into the msg variable. This function must be used exclusively within an event procedure [on mostAMSMessage](../EventProcedures/CAPLfunctionOnMOSTAMSMessage.md).

## Parameters

- **msg**: Variable of the type mostAmsMessage.
- **count**: Number of use data bytes that have to be copied.

## Return Values

—

## Example

The following program section copies 1000 bytes of a message's useful data to the local variable msg on Channel 1. Afterwards the contents of byte 500 are output to the Write Window.

```plaintext
on mostAMSMessage MsgChannel1.*
{
   mostAMSMessage * msg = { DLC = 1000 };
   GetThisMessage(msg, 1000);
   write("Byte 500: %02X", msg.byte(500));
}
```
