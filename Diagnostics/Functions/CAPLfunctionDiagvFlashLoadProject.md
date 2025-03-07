[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashLoadProject.md)

[CAPL Functions](../../CAPLfunctions.md) » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » vFlashLoadProject

# vFlashLoadProject

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: This function replaces the function `vFlashLoad`. With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel. See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```plaintext
void vFlashLoadProject(char projectPath[]);
```

## Description

Loads the provided vFlash project stored under given path. A call to CAPL callback function `vFlashLoadProjectCompleted` will indicate that the project was loaded. Further API calls are only allowed after callback was called!

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

- **projectPath**: Path to the flash project file.

## Return Values

—

## Example

```plaintext
//...
vFlashLoadProject("Firmware1.vflashpack");
}

void vFlashLoadProjectCompleted(long statusCode)
{
  write("Loading of project completed with status %d", statusCode);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)