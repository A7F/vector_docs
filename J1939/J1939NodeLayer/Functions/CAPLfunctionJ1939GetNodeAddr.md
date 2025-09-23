# J1939GetNodeAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetNodeAddr( dword ecuHandle );
```

## Description

This function returns the current address of a logical ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

- current ECU address
- 0xFE if the address is the J1939 NULL address. If this function is called with an invalid handle, the function returns 0xFFFF.

## Example

```plaintext
addr = J1939GetNodeAddr(ecuHandle);
```
