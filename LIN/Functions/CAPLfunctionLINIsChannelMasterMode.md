[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINIsChannelMasterMode.md)

# linIsChannelMasterMode

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linIsChannelMasterMode

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
long linIsChannelMasterMode();
```

## Description

This function returns 1 if the network channel given by the current bus context is running in master mode, 0 otherwise. See [SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md) for how to change the current bus context.

The channel’s master mode setting can be changed at any time using the function [linSetChannelMasterMode](CAPLfunctionLINSetChannelMasterMode.md).

See also [Master Mode of the LIN Hardware](../../../CANoeCANalyzer/LIN/HowTos/LINHardwareMasterMode.md) for details on the LIN channel master mode.

## Parameters

—

## Return Values

1 if the current bus context’s LIN channel is in master mode, 0 otherwise

## Example

```c
if (!linIsChannelMasterMode())
{
  // manually activate Master mode on LIN hardware
  linSetChannelMasterMode(1);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)