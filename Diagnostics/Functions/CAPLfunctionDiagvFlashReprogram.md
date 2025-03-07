[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Diagnostics/Functions/CAPLfunctionDiagvFlashReprogram.md)

**CAPL Functions** » [Diagnostics](../CAPLfunctionsDiagnosticsOverview.md) » vFlashReprogram

# vFlashReprogram

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
This function replaces the function `vFlashStart`. With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```plaintext
void vFlashReprogram();
```

## Description

Starts the flashing procedure. The progress will be indicated by calls to the optional callback `vFlashProgramProgressCallback`. The procedure has finished when CAPL callback `vFlashReprogramCompleted` is called.

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

—

## Return Values

1. Flashing was started

## Example

```plaintext
FlashReprogram();
}

void vFlashProgramProgressCallback(dword progressInPercent, dword remainingTimeInS)
{
  // Do not print on every progress callback, but only in 10% steps
  DWORD sProgress = 0;
  if (progressInPercent < sProgress)
    sProgress = 0; // reset progress stored
  if (progressInPercent < 100 && (progressInPercent - sProgress) >= 10)
  {
    write("Progress: %3u%%, %us remaining", progressInPercent, remainingTimeInS);
    sProgress = progressInPercent - (progressInPercent % 10);
  }
}

void vFlashReprogramCompleted(long status)
{
  write("Reprogramming completed with status %d", status);
}
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)