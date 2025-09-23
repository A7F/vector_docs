[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/EventProcedures/CAPLfunctionOnMOSTRawMessage.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » on mostRawMessage

# on mostRawMessage

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

## Function Syntax

`on mostRawMessage;`

## Description

`on mostRawMessage` is called on the receipt of MOST frames whose type isn't **Normal**.

These are **RemoteRead**, **RemoteWrite**, **Alloc**, **Dealloc** and **GetSource**. See [Selectors](../CAPLfunctionsMOSTOverview.md) for the applicable selectors. The command `output(this)` can be used for forwarding the message in a node chain.

If the event procedure should only react to messages on channel 1 this is defined as follows:

`on MsgChannel1.mostRawMessage`

## Parameters

—

## Return Values

—

## Example

—
