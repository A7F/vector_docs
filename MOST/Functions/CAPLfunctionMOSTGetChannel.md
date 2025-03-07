[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/MOST/Functions/CAPLfunctionMOSTGetChannel.md)

[CAPL Functions](../../CAPLfunctions.md) » [MOST](../CAPLfunctionsMOSTOverview.md) » mostGetChannel

# mostGetChannel

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

## Function Syntax

```plaintext
mostGetChannel ();
```

## Description

This query returns the number of the MOST channel to which the CAPL node is connected in the Simulation Setup.

This query is especially useful with nodes that are only connected to one MOST channel in the Simulation Setup. The return value can be used directly as a parameter for all CAPL functions that expect specification of a channel, e.g. in driving the network interface.

With the help of this function CAPL programs can be created such that they are independent of channel numbers. By proper configuration of the Simulation Setup the user can choose the MOST interface over which the node should be operated.

## Parameters

—

## Return Values

- **0**: the node is not connected to any MOST channel in the Simulation Setup
- **1..16**: the allocated MOST channel
- **0xFFFF**: The node is connected to more than one MOST channel and may operate as a Gateway. The user must choose, on a case-by-case basis, the MOST channel over which the node should operate.

  In this case, channel numbers and bus names from the Simulation Setup are determined by the [getBusContext](../../Other/Functions/CAPLfunctionGetBusContext.md) or [getBusNameContext](../../Other/Functions/CAPLfunctionGetBusNameContext.md) function.

## Example

—

[getBusNameContext](../../Other/Functions/CAPLfunctionGetBusNameContext.md) • [getBusContext](../../Other/Functions/CAPLfunctionGetBusContext.md) • [mostStrictChannelMapping](CAPLfunctionMOSTStrictChannelMapping.md) • [mostApplicationNode](CAPLfunctionMOSTApplicationNode.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) • [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)