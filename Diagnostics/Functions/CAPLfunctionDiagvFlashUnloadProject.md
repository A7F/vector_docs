[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashUnloadProject.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » vFlashUnloadProject

# vFlashUnloadProject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This function replaces the function `vFlashUnload`. With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel. See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```plaintext
void vFlashUnloadProject();
```

## Description

Unloads the current vFlash project. The CAPL callback `vFlashUnloadProjectCompleted` will be called when the unloading completed and further API calls are possible.

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

—

## Return Values

—

## Example

```plaintext
// ...
vFlashUnloadProject();
}

void vFlashUnloadProjectCompleted(enum vFlashStatusCode statusCode)
{
  write("Unloading project completed, another project can be loaded.");
}
```

[vFlashLoadProject](CAPLfunctionDiagvFlashLoadProject.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)