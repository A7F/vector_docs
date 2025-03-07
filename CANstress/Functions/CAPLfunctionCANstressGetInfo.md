[Open topic with navigation](../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/CANstress/Functions/CAPLfunctionCANstressGetInfo.md)

# CANstressGetInfo

[CAPL Functions](../../CAPLfunctions.md) » [CANstresss](../CAPLfunctionsCANstressOverview.md) » CANstressGetInfo

**Valid for:** CANoe DE

**Note**  
So that the call can be executed successfully, there must be a connection between the CANstress software and the CANstress hardware. Only in this case can the information for the CANstress hardware (firmware, CAN interface, serial number) be acquired correctly.

## Function Syntax

```
long CANstressGetInfo( char softwareVersion[], long swVersionBufLen, char firmwareVersion[], long fwVersionBufLen, char serialNumber[], long snBufLen, char canInterface1[], long if1BufLen, char canInterface2[], long if2BufLen );
```

## Description

Delivers information on CANstress software and the connected CAN hardware.

## Parameters

- **softwareVersion**: Buffer in which the version of the software is written (recommended buffer size: 20 Byte).
- **swVersionBufLen**: Size of the buffer in which the software version is written (in bytes).
- **firmwareVersion**: Buffer in which the version of the firmware is written (recommended buffer size: 10 Byte).
- **fwVersionBufLen**: Size of the buffer in which the firmware version is written (in bytes).
- **serialNumber**: Buffer in which the serial number of the CANstress hardware is written (recommended buffer size: 20 Byte).
- **snBufLen**: Size of the buffer in which the hardware serial number is written (in bytes).
- **canInterface1**: Buffer in which the type of the CAN interface 1 of the CANstress hardware is written (recommended buffer size: 40 Byte).
- **if1BufLen**: Size of the buffer in which the type of the CAN interface1 is written (in bytes).
- **canInterface2**: Buffer in which the type of the CAN interface 2 of the CANstress hardware is written (recommended buffer size: 40 Byte).
- **if2BufLen**: Size of the buffer in which the type of the CAN interface 2 is written (in bytes).

## Return Values

- **0**: On successful call.
- **-1**: In case of error.

## Example

—

© Vector Informatik GmbH  
CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3  
[Contact/Copyright/License](../../../Shared/ContactCopyrightLicense.md)  
[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)