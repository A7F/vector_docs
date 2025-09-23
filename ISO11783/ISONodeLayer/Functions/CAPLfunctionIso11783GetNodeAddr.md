# Iso11783GetNodeAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword Iso11783GetNodeAddr( dword ecuHandle );
```

## Description

This function returns the current address of a logical ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- Current ECU address
- `0xFE` if the address is the ISO11783 NULL address. If this function is called with an invalid handle, the function returns `0xFFFF`.

## Example

```c
addr = Iso11783GetNodeAddr(ecuHandle);
```
