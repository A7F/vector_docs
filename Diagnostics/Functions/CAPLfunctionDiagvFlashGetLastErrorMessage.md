# vFlashGetLastErrorMessage

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**

With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.

See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```c
void vFlashGetLastErrorMessage();
```

## Description

Requests a call to the CAPL callback `vFlashErrorMessage` containing information on the error that occurred.

## Parameters

—

## Return Values

—

## Example

```c
// ...Error occurred...
vFlashGetLastErrorMessage();
}

void vFlashErrorMessage(char errorMsg[])
{
  write("Error %s", errorMsg);
}
```
