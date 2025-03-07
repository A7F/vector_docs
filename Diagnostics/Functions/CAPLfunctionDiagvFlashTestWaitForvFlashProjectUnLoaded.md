[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashTestWaitForvFlashProjectUnLoaded.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » TestWaitForvFlashProjectLoaded, TestWaitForvFlashProjectUnloaded

# TestWaitForvFlashProjectLoaded, TestWaitForvFlashProjectUnloaded

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

`long TestWaitForvFlashProjectLoaded(char projectPath[]);`  
`long TestWaitForvFlashProjectUnloaded()`

## Description

Waits until the given packed vFlash project (including flashware) is loaded or unloaded.

## Parameters

- **projectPath**: Path to the packed vFlash project, a **vflashpack** file typically.

## Return Values

- **1**: Success
- **1031**: Project file does not exist under the given path
- **1032**: Project could not be loaded, e.g. a referenced file is missing

Other: please refer to `enum vFlashStatusCode` in `Reusable\CAPL_Includes\vFlash\Utilities.cin`

## Example

—

[TestWaitForvFlashReprogrammed](CAPLfunctionDiagvFlashTestWaitForvFlashReprogrammed.md)

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)