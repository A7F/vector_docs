[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/AUTOSARethIL/Functions/CAPLfunctionAREthSetVerbosity.md)

**CAPL Functions** » **Ethernet** » **AUTOSAR Eth IL** » AREthSetVerbosity

# AREthSetVerbosity

[Valid for: CANoe DE • CANoe4SW DE](../../../../Shared/FeatureAvailability.md)

## Function Syntax

```plaintext
long AREthSetVerbosity( long verbosity);
```

## Description

Sets the verbosity level of AUTOSAR Eth IL messages in the Write Window.

## Parameters

- **verbosity**: Verbosity level:
  - 0: Silent - do not write messages to the Write Window
  - 1: Error - write only error messages (default)
  - 2: Warning - write warning and error messages
  - 3: Information - write information, warning and error messages

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../CAPLfunctionsAREthILErrorCodes.md)

## Example

```plaintext
on key '0'
{
  char buffer[1024];
  // set verbosity level to "Silent" mode
  if(AREthSetVerbosity(0) == 0)
  {
    write("AUTOSAR Eth IL verbosity level was set to mode \"silent\"");
  } // if
  else
  {
    // check if last function was executed correct
    AREthGetLastErrorText(elcount(buffer),buffer);
    write("Error setting verbosity level if AUTOSAR Eth IL: %s", buffer);
  } // else
}
```

[See Also](javascript:void(0);)
