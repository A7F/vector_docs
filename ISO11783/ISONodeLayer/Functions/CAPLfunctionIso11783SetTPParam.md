# Iso11783SetTPParam

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783SetTPParam( dword ecuHandle, dword what, dword value );
```

## Description

Changing transport protocol settings.

## Parameters

- **ecuHandle**: ECU handle
- **what**: Index of the parameter
  - **1**: Maximum number of bytes, which can be transferred
    - Value Range: 8 < value < 117440505
    - Initial Value: 100 MByte
  - **2**: Number of packets, which are requested by CTS
    - Value Range: 1 < value < 255
    - Initial Value: 1
  - **3**: Number of packets, which are requested by ECTS (Extended TP)
    - Value Range: 1 < value < 255
    - Initial Value: 64
  - **8**: Number of packets, which is used with RTS
    - Value Range: 1 < value < 255
    - Initial Value: 255
  - **10**: Set the used debug level
    - Value Range: 0 < value < 3
    - Initial Value: 2
  - **11**: Use of network management
    - 0 - deactivate network management
    - 1 - activate network management
    - Value Range: 0 < value < 1
    - Initial Value: 1
  - **12**: Target address, which is used for BAM
    - 0 - target address is 0xFF
    - 1 - specific target address is used
    - Value Range: 0 < value < 1
    - Initial Value: 0
  - **13**: Priority used by the transport protocol
    - Value Range: 0 < value < 7
    - Initial Value: 7
- **value**: New value

## Return Values

0 on success or [error code](../CAPLfunctionsISONLErrorCodes.md)

## Example

```c
Iso11783SetTPParam(ecuHdl, 1, 32*1024);
```
