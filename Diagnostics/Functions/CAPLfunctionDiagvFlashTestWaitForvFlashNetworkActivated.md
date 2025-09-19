# TestWaitForvFlashNetworkActivated

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```
long TestWaitForvFlashNetworkActivated();
```

## Description

Waits until the vFlash has started the FlexRay network in case flashing is performed using FlexRay, i.e. both communication controllers are in normal active state.

## Parameters

—

## Return Values

- **1**: Success
- **1036**: Network activation failed, e.g. incorrect hardware setup

Other: please refer to `enum vFlashStatusCode` in `Reusable\CAPL_Includes\vFlash\Utilities.cin`

## Example

—

[TestWaitForvFlashReprogrammed](CAPLfunctionDiagvFlashTestWaitForvFlashReprogrammed.md)
