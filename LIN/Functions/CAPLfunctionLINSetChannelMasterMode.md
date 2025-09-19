[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetChannelMasterMode.md)

# linSetChannelMasterMode

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetChannelMasterMode

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**  
In real measurement mode, this function is only available starting with LIN Firmware version 1.75. Please verify, in the hardware configuration dialog in the selected LIN channel, the LIN firmware version. In simulated mode, this function is always available.

## Function Syntax

```plaintext
long linSetChannelMasterMode(long masterMode);
```

## Description

By calling this function, the channel specified by the current bus context can be switched to master or slave mode. See [SetBusContext](../../Other/Functions/CAPLfunctionSetBusContext.md) for how to change the current bus context. The impacts of switching a LIN hardware channel to master or slave are described in [Master Mode of the LIN Hardware](../../../CANoeCANalyzer/LIN/HowTos/LINHardwareMasterMode.md). In simulated mode, the only effect is that sending a LIN header in slave mode (by calling [linTransmitHeader](CAPLfunctionLINTransmitHeader.md) or output(linFrame) with linFrame.RTR = 1) will have no effect.

This function can be called at any time. If a LIN scheduler is defined by using a LDF, calling this function will deactivate the scheduler when changing to slave mode. When changing back to master mode, the scheduler’s running state will be restored to its state before changing to slave mode.

A channel configured to slave mode by the settings of the network hardware dialog still can contain a master node defined in an attached LDF file. The scheduler of that channel will be automatically activated when the channel is switched to master mode.

## Parameters

- **masterMode**  
  This parameter specifies whether the Master mode will be enabled or disabled on the LIN channel.
  - 0: Disable
  - 1: Enable

## Return Values

Returns 1 if changing the channel master mode succeeded, 0 otherwise.

## Example

```plaintext
linSetChannelMasterMode(1); // manually activate the Master mode on LIN hardware
```

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
