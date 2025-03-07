[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashTestWaitForvFlashNetworkActivated.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » TestWaitForvFlashNetworkActivated

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

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)