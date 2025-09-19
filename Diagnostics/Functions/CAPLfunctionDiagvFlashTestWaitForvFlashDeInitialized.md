# TestWaitForvFlashInitialized , TestWaitForvFlashDeinitialized

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE

**Note**  
With the following function(s) a CAPL program can use [vFlash](../../../CANoeCANalyzer/VTPPlatformManager/CANoePlugIN/CANoePlugInvFlashCompact.md) to program an ECU. vFlash has to be installed on the system running the RT kernel.  
See also: [vFlash Automation (Sample Configuration)](../../../SampConf/Programming/CANoe/vFlashAutomation/vFLASHsampCN.md).

## Function Syntax

```
long TestWaitForvFlashInitialized();
long TestWaitForvFlashDeinitialized();
```

## Description

Waits until the vFlash library is initialized/deinitialized. A call to `TestWaitForvFlashDeinitialized` is mandatory if any other call to a function of the vFlash API is made.

## Parameters

—

## Return Values

- **1**: Success
- **1010**: Initialization error, e.g. vFlash not installed (correctly)
- other: please refer to `enum vFlashStatusCode` in `Reusable\CAPL_Includes\vFlash\Utilities.cin`

## Example

```c
includes
{
  #include "vFlash\Utilities.cin"
}
variables
{
  char gFlashpack[cMaxPathNameLen] = "";
}
enum vFlashStatusCode InitializeFlashProcess()
{
  enum vFlashStatusCode resultCode;
  char errorText[gkMaxErrorTextLength];

  //----- Initialize vFlash Library -----
  resultCode = (enum vFlashStatusCode) TestWaitForvFlashInitialized();
  if (resultCode != Success)
  {
    TestWaitForvFlashLastErrorMessage(errorText, 1024);
    snprintf(errorText, gkMaxErrorTextLength, "vFlash initialization error: %s", errorText);
    write(errorText);
    TestStepFail("TestWaitForvFlashInitialized", errorText);
  }
  else
  {
    TestStepPass("TestWaitForvFlashInitialized", "vFlash initialized successfully");
  }
  return resultCode;
}
```

[TestWaitForvFlashReprogrammed](CAPLfunctionDiagvFlashTestWaitForvFlashReprogrammed.md)
