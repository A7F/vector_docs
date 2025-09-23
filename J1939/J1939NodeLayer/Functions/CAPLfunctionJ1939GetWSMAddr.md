# J1939GetWSMAddr

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```
dword J1939GetWSMAddr( dword ecuHandle );
```

## Description

This function returns the address of the Working Set Master, which is assigned to this ECU.

## Parameters

- **ecuHandle**: ECU handle

## Return Values

Address of the Working Set Master for this ECU or the Null-Address (0xFE)

## Example

```plaintext
addr = J1939GetWSMAddr( ecuHdl );
```
