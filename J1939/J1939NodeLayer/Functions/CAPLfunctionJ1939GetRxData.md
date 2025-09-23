# J1939GetRxData

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetRxData( dword bufferSize, char buffer[] );
```

## Description

An auxiliary function for receiving PG data within a callback function.

The DLL interface will not permit you to transfer data arrays via callback. Therefore it serves the purpose of "retrieving" data from the node layer. Since this function is called within a callback, there is no need to transfer an ECU handle. If the function is called from outside of a callback, the call has no effect.

## Parameters

- **bufferSize**: size of the buffer
- **buffer**: buffer which should receive the data

## Return Values

Number of bytes copied

## Example

```c
char data[100];
dword count;

count = J1939GetRxData( elCount(data), data );
```
