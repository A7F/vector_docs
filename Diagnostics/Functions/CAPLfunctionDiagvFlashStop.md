# vFlashStop

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**: With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel. See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```
void vFlashActivateNetwork();
```

## Description

Stops the flashing procedure. The completion of the stopping is indicated by a call to the CAPL function `vFlashStopCompleted`.

**Note**: This event-driven API is only needed outside of test modules or test units.

## Parameters

—

## Return Values

—

## Example

```c
//...
vFlashStop();
}

void vFlashStopCompleted(long statusCode)
{
  write("Stopping flashing completed with status %d", status);
  // Unload the project to be able to load a different one
  vFlashUnloadProject();
}
```

[vFlashReprogram](CAPLfunctionDiagvFlashReprogram.md)
