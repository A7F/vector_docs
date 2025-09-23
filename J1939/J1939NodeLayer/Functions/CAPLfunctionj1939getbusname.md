[Open topic with navigation](../../../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/J1939/J1939NodeLayer/Functions/CAPLfunctionj1939getbusname.md)

**CAPL Functions** » **J1939** » **J1939 NL** » **J1939GetBusName**

# J1939GetBusName

[Valid for: CANoe DE](../../../../Shared/FeatureAvailability.md) • CANoe4SW DE

## Function Syntax

```
dword J1939GetBusName( dword busHandle, dword bufferSize, char buffer[] );
```

## Description

Gets a bus name.

## Parameters

- **busHandle**: bus handle, see also [J1939GetBus](CAPLfunctionj1939getbus.md)
- **bufferSize**: size of buffer in Bytes
- **buffer**: bus name is copied into this buffer

## Return Values

- **0**: function has been executed successfully
- **< 0**: an error has occurred

## Example

```c
char busName[32];
J1939GetBusName( busHandle, elCount(busName), busName );
```
