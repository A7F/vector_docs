# vFlashDeinitialize, vFlashInitialize

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```plaintext
void vFlashInitialize();
void vFlashDeinitialize();
```

## Description

Initializes (deinitializes) vFlash. Further API calls are only allowed after the CAPL callback **vFlashInitializeCompleted** (or **vFlashDeinitializeCompleted**) was called!

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

—

## Return Values

—

## Example

—
