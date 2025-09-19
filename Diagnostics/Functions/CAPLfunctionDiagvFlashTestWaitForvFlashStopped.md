# TestWaitForvFlashStopped

[Valid for](../../../Shared/FeatureAvailability.md):  CANoe DE

**Note**

With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.

See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```
long TestWaitForvFlashStopped();
```

## Description

Aborts the active flashing process and waits until the flashing has stopped.

## Parameters

—

## Return Values

- **1**: Success
- **1020**: Stop failed

other: please refer to `enum vFlashStatusCode` in `Reusable\CAPL_Includes\vFlash\Utilities.cin`

## Example

—

[TestWaitForvFlashReprogrammed](CAPLfunctionDiagvFlashTestWaitForvFlashReprogrammed.md)
