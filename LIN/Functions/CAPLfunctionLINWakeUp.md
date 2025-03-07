[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINWakeUp.md)

**CAPL Functions** » [LIN](../CAPLfunctionsLINOverview.md) » linWakeup

# linWakeup

**Valid for**: CANoe DE

## Function Syntax

```plaintext
long linWakeup(); // form 1
linWakeup(dword ttobrk, dword wakeupSignalCount, dword widthInMicSec); // from 2
```

## Description

Sends wakeup signals. Wakeup signals can only be sent while the LIN hardware is in Sleep mode. If no parameters are given, the default parameters or the parameters configured with [linSetWakeupTimings](CAPLfunctionLINSetWakeupTimings.md) are used. Wake up timings can be configured per node for nodes defined in a LIN database. If no database is used the signature using wake parameters shall be used.

**Note**: When LIN hardware is not in Sleep mode calling this function will have no effect.

## Parameters

- **ttobrk**: This parameter specifies the time difference between the transmissions of two consecutive Wakeup frames, i.e. the time between end of one wakeup frame and start of the next one. Units of this parameter as well as default value depend on the hardware settings (see Hardware Configuration: LIN).  
  Value range (for units expected in bit times): 20..50000  
  Value range (for units expected in ms): 1..65536

- **wakeupSignalCount**: Sets the number of Wakeup frame retransmissions.  
  Value range: 1…255  
  Default value depends on the hardware settings (see [Hardware Configuration: LIN](../CAPLfunctionsLINHardwareConfiguration.md)).

- **widthInMicSec**: This parameter sets the width of the wakeup frame to be sent in microseconds. The resolution is 50 µs. This parameter is only used by slave nodes applying LIN protocol starting with version 2.0.  
  Value range: 250..5000 µs  
  Default value depends on the hardware settings (see [Hardware Configuration: LIN](../CAPLfunctionsLINHardwareConfiguration.md)).

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
// send a wakeup signal via a keyboard event
on key 'w'
{
  linWakeup();
}
// send wakeup signal 3 times with 150 ms delay between 2 consecutive signals and a length of 300 us
linWakeup(150, 3, 300);
...
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)