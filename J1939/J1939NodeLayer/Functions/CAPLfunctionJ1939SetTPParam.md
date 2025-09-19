[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionJ1939SetTPParam.md)

[CAPL Functions](../../../CAPLfunctions.md) » [J1939](../../CAPLfunctionsJ1939StartPage.md) » [J1939 NL](../CAPLfunctionsJ1939NLOverview.md) » J1939SetTPParam

# J1939SetTPParam

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939SetTPParam( dword ecuHandle, dword what, dword value );
```

## Description

Changing transport protocol settings.

## Parameters

- **ecuHandle**: ECU handle
- **what**: index of the parameter
  - **1**: Maximum number of bytes, which can be transferred
    - **Value Range**: 8 < value < 117440505
    - **Initial Value**: 100 MByte
  - **2**: Number of packets, which are requested by CTS
    - **Value Range**: 1 < value < 255
    - **Initial Value**: 1
  - **3**: Number of packets, which are requested by ECTS (Extended TP)
    - **Value Range**: 1 < value < 255
    - **Initial Value**: 64
  - **8**: Number of packets, which is used with RTS
    - **Value Range**: 1 < value < 255
    - **Initial Value**: 255
  - **10**: Set the used debug level
    - **Value Range**: 0 < value < 3
    - **Initial Value**: 2
  - **11**: Use of network management
    - **Value Range**: 0 < value < 1
    - **Initial Value**: 1
    - 0: deactivate network management
    - 1: activate network management
  - **12**: target address, which is used for BAM
    - **Value Range**: 0 < value < 1
    - **Initial Value**: 0
    - 0: target address is 0xFF
    - 1: specific target address is used
  - **13**: priority used by the transport protocol
    - **Value Range**: 0 < value < 7
    - **Initial Value**: 7
- **value**: new value

## Return Values

0 on success or [error code](../CAPLfunctionsJ1939NLErrorCodes.md)

## Example

```c
J1939SetTPParam(ecuHdl, 1, 32*1024);
```

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../../../Shared/ContactCopyrightLicense.md)

[Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
