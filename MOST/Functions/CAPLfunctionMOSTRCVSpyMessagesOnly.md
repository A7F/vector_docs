[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTRCVSpyMessagesOnly.md)

**CAPL Functions** » [MOST](../CAPLfunctionsMOSTOverview.md) » mostRcvSpyMessagesOnly

# mostRcvSpyMessagesOnly

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

`mostRcvSpyMessagesOnly()` may only be called within the [on preStart](../../Other/EventProcedures/CAPLfunctionsEventproceduresMeasurementSystem.md) function of the CAPL program!

## Function Syntax

`mostRcvSpyMessagesOnly ();`

## Description

The MOST message handling routines of this node are only called if the message was received by the Spy of the network interfaces.

This mode is especially useful for nodes that act as pure observers or – with the help of the Spy – are used to perform cross-node analysis.

Queries such as "if (!this.MOST_IsSpy) return;" have been eliminated in the message handling routines, because the message handling routines are no longer called by node and Spy messages.

## Parameters

—

## Return Values

—

## Example

—

[mostGetChannel](CAPLfunctionMOSTGetChannel.md) • [mostStrictChannelMapping](CAPLfunctionMOSTStrictChannelMapping.md) • [mostApplicationNode](CAPLfunctionMOSTApplicationNode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
