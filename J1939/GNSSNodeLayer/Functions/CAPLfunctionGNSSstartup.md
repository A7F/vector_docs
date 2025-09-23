[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/GNSSNodeLayer/Functions/CAPLfunctionGNSSstartup.md)

**CAPL Functions** » **J1939** » **GNSS NL** » **GNSSStartUp**

# GNSSStartUp

**Valid for**: CANoe DE • CANoe4SW DE

## Function Syntax

```
dword GNSSStartUp( byte name[8], uint address )
```

## Description

This function sets up a logical node within a CANoe network node. The `name` parameter is used to transfer the J1939 device name of the logical node. Care should be taken not to assign any name twice on the network.

## Parameters

- **name**: Name of the device
- **address**: Address of the device

## Return Values

[Error code](../CAPLfunctionsGNSSNLErrorCodesGetLastError.md)

## Example

```c
char name[8];
GNSSMakeName(name, 1, 0, 0, 0, 28, 0, 0, 0, 0);
GNSSStartUp(name, 3);
```
