# J1939GetEcuState

[Valid for](../../../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Function Syntax

```plaintext
dword J1939GetEcuState(dword ecuHandle);
dword J1939GetEcuState(dbNode dbNode);
```

## Description

Returns the current state of the ECU.

## Parameters

- **ecuHandle**: ECU handle
- **dbNode**: node from database

## Return Values

- **0**: initialized
- **1**: claiming
- **2**: online
- **3**: offline

## Example

```plaintext
if (J1939GetEcuState( handle ) == 2) {
  write( "ECU is online" );
}
```
