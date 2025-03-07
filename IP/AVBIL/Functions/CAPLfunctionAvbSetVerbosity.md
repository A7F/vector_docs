[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AVBIL/Functions/CAPLfunctionAvbSetVerbosity.md)

**CAPL Functions** » [Ethernet](../../CAPLEthernetStartPage.md) » [AVB IL](../CAPLfunctionsAVBILOverview.md) » AvbSetVerbosity

# AvbSetVerbosity

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword AvbSetVerbosity(long verbosity);
```

## Description

Sets the verbosity level of AVB IL messages in the Write Window.

## Parameters

- **verbosity**  
  Verbosity level:
  - 0: Silent - do not write messages to the Write Window
  - 1: Error - write only error messages (default)
  - 2: Warning - write warning and error messages
  - 3: Information - write information, warning and error messages

## Return Values

Number of copied characters.

## Example

```c
on key '0'
{
  char buffer[1024];
  // set verbosity level to "Silent" mode
  if (AvbSetVerbosity(0) == 0)
  {
    write("AVB IL verbosity level was set to mode \"silent\"");
  }
  else
  {
    // check if last function was successfully executed
    AvbGetLastErrorText(elcount(buffer), buffer);
    write("Error setting verbosity level if AVB IL: %s", buffer);
  }
}
```

[See Also](javascript:void(0);)