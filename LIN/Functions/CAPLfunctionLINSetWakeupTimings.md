[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/LIN/Functions/CAPLfunctionLINSetWakeupTimings.md)

[CAPL Functions](../../CAPLfunctions.md) » [LIN](../CAPLfunctionsLINOverview.md) » linSetWakeupTimings

# linSetWakeupTimings

[Valid for](../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
linSetWakeupTimings(long ttobrk, long wakeupSignalcount, dword widthInMicSec); // form 1
linSetWakeupTimings(long ttobrk, long wakeupSignalcount, dword widthInMicSec, char nodeName[]); // form 2
```

## Description

Configures wake-up timings. Wake-up timings can be configured per node for nodes defined in a LIN database.

## Parameters

- **ttobrk**  
  This parameter specifies the time difference between the transmissions of two consecutive Wakeup frames, i.e., the time between the end of one wakeup frame and the start of the next one. Units of this parameter as well as default value depend on the hardware settings (see [Hardware Configuration: LIN](../CAPLfunctionsLINHardwareConfiguration.md)).  
  Value range (for units expected in bit times): 20..50000  
  Value range (for units expected in ms): 1..65536

- **wakeupSignalCount**  
  Sets the number of Wakeup frame retransmissions.  
  Value range: 1..255  
  Default value depends on the hardware settings (see [Hardware Configuration: LIN](../CAPLfunctionsLINHardwareConfiguration.md)).

- **widthInMicSec**  
  This parameter sets the width of the wakeup frame to be sent in microseconds. The resolution is 50 µs. This parameter is only used by LIN2.0 slave nodes.  
  Value range: 250..5000 µs  
  Default value depends on the hardware settings (see [Hardware Configuration: LIN](../CAPLfunctionsLINHardwareConfiguration.md)).

- **nodeName**  
  Name of a LIN node defined in the database.

## Return Values

On success, a value unequal to zero, otherwise zero.

## Example

```plaintext
// Configures the wake up timings for the database node "LINMaster".
linSetWakeupTimings(150, 3, 250, "LINMaster")

// send a wakeup signal via a keyboard event within the CAPL program of the node 
// "LINMaster". The configured timings will be used.
on key 'w'
{
  linWakeup();
}
```

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)