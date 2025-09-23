# Iso11783GetEcuState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword Iso11783GetEcuState(dword ecuHandle);
dword Iso11783GetEcuState(dbNode dbNode);
```

## Description

Returns the current state of the ECU.

## Parameters

- **ecuHandle**: ECU handle
- **dbNode**: Node from database

## Return Values

- **0**: initialized
- **1**: claiming
- **2**: online
- **3**: offline

## Example

```plaintext
if (Iso11783GetEcuState(handle) == 2) {
  write("ECU is online");
}
```
