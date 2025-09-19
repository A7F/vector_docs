# TestWaitForvFlashReprogrammed

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.

See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```
long TestWaitForvFlashReprogrammed();
```

## Description

Starts the flashing process and waits until it has finished.

## Parameters

—

## Return Values

- **1**: Success
- **1030**: No project is loaded, e.g. loading a project has failed

Other: please refer to `enum vFlashStatusCode` in `Reusable\CAPL_Includes\vFlash\Utilities.cin`

## Example

—
