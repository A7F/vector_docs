[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/IP/SOMEIPIL/Functions/CAPLfunctionSomeIpSetVerbosity.md)

**CAPL Functions** » **Ethernet** » **SOME/IP IL** » **SomeIpSetVerbosity**

# SomeIpSetVerbosity

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
long SomeIpSetVerbosity(long verbosity);
```

## Description

Sets the verbosity level of SOME/IP IL messages in the Write Window.

## Parameters

- **verbosity**: Verbosity level:
  - 0: Silent - do not write messages to the Write Window
  - 1: Error - write only error messages (default)
  - 2: Warning - write warning and error messages
  - 3: Information - write information, warning and error messages

## Return Values

- **0**: The function was successfully executed
- **>0**: [Error code](../../CAPLfunctionsSOMEIPILErrorCodes.md)

## Example

```plaintext
on key '0'
{
  char buffer[1024];
  // set verbosity level to "Silent" mode
  if(SomeIpSetVerbosity(0) == 0)
  {
    write("SOME/IP IL verbosity level was set to mode \"silent\"");
  } // if
  else
  {
    // check if last function was executed correct
    SomeIpGetLastErrorText(elcount(buffer),buffer);
    write("Error setting verbosity level if SOME/IP IL: %s", buffer);
  } // else
}
```

[See Also](javascript:void(0);)
```markdown